<template>
  <img alt="logo" class="logo" src="./assets/electron.svg" />
  <div class="creator">Convert Text To Html</div>
  <div class="text">
    Convertir
    <span class="vue">Texto</span>
    a
    <span class="ts">HTML</span>
  </div>
  <article class="article_content_panel">
    <section class="section_subpanel_container">
      <p class="tip">Ingrese el texto y personalizelo a su gusto.</p>
      <section class="section_subpanel">
        <quill-editor theme="snow" toolbar="minimal" @text-change="getHtmlFromEditor" />
      </section>
    </section>
    <section class="section_subpanel_container">
      <p class="tip">A quí podrá ver el texto en formato HTML.</p>
      <section class="section_subpanel" style="padding-top: 50px">
        <code id="code_html_to_export" class="code_html_to_export">{{ contentTextWithHtml }}</code>
        <div class="action actions_code_container">
          <a target="_blank" rel="noreferrer" @click="copyTextWithHtml">Copiar</a>
        </div>
      </section>
    </section>
  </article>
</template>
<script setup lang="ts">
import { QuillEditor } from '@vueup/vue-quill'
import './assets/quillEditorDefault.css'
import { ref } from 'vue'

const contentTextWithHtml = ref('')

function getHtmlFromEditor() {
  const contentEditor = document.getElementsByClassName('ql-editor')
  if (contentEditor && contentEditor.length > 0) {
    contentTextWithHtml.value = contentEditor[0].getHTML()
  }
}

function copyTextWithHtml() {
  navigator.clipboard
    .writeText(contentTextWithHtml.value)
    .then(() => {
      alert('Texto copiado al portapapeles')
    })
    .catch((err) => {
      console.error('Error al copiar el texto: ', err)
    })
}
</script>
<style>
.article_content_panel {
  display: flex;
  height: 60vh;
  width: 80vw;
}

.section_subpanel_container {
  width: 50%;
}

.section_subpanel {
  width: 100%;
  height: 80%;
  min-height: 200px;
  position: relative;
  border: 1px solid var(--ev-button-alt-text);
  border-radius: 5px;
  overflow: auto;
}

.ql-toolbar.ql-snow {
  position: sticky;
  top: 0;
  z-index: 1;
  background-color: var(--ev-button-alt-bg);
}

.code_html_to_export {
  background-color: transparent;
}

.actions_code_container {
  position: absolute;
  top: 0;
  right: 0;
}

.code_html_to_export {
  width: 100%;
  display: block;
  height: 100%;
  color: var(--ev-c-text-1);
  padding: 12px;
  overflow: auto;
}
</style>
