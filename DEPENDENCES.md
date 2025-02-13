# Dependencias

An Electron application with Vue and TypeScript

### Dependencias base electron-vite

A continuación se enuncian las dependencias que vienen por defecto al crear un proyecto en electron-vite:

```json
"dependencies": {
"@electron-toolkit/preload": "^3.0.0",
"@electron-toolkit/utils": "^3.0.0",
"electron-updater": "^6.1.7"
},
"devDependencies": {
"@electron-toolkit/eslint-config": "^1.0.2",
"@electron-toolkit/eslint-config-ts": "^2.0.0",
"@electron-toolkit/tsconfig": "^1.0.1",
"@rushstack/eslint-patch": "^1.10.3",
"@types/node": "^20.14.8",
"@vitejs/plugin-vue": "^5.0.5",
"@vue/eslint-config-prettier": "^9.0.0",
"@vue/eslint-config-typescript": "^13.0.0",
"electron": "^31.0.2",
"electron-builder": "^24.13.3",
"electron-vite": "^2.3.0",
"eslint": "^8.57.0",
"eslint-plugin-vue": "^9.26.0",
"prettier": "^3.3.2",
"typescript": "^5.5.2",
"vite": "^5.3.1",
"vue": "^3.4.30",
"vue-tsc": "^2.0.22"
}
```

## Dependencias añadidas

### dependencies

#### @vueup/vue-quill

Permite mostrar un editor de texto enriquecido

```json
"dependencies": {
"@vueup/vue-quill": "^1.2.0",
}
```

#### js-beautify

Permite formatear textos. Esto es usado para formatear el texto convertido y mostrarselo con un mejor formato al
usuario.

```json
"dependencies": {
"js-beautify": "^1.15.1"
}
```

### devDependencies

#### @vue/language-server

Debido a problemas presentados con el IDE de jetbrains en su servidor para vue,
se instala esta dependencia para que el IDE pueda mostrar todas las ayudas en tipado, correccion y errores del proyecto.

```json

"devDependencies": {
"@vue/language-server": "^2.1.6",
}
```

#### @types/js-beautify

Tipado para la dependencia `js-beautify`

```json

"devDependencies": {
"@types/js-beautify": "^2.1.6",
}
```