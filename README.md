Blank Sass Layout

    NPM commands
    npm init
    npm install sass npm-run-all concat postcss-cli autoprefixer --save-dev
    npm install live-server -g

// JSON DEV SCRIPTS

    "watch:sass": "sass sass/main.scss css/style.css -w",
    "devserver": "live-server",
    "start": "npm-run-all --parallel devserver watch:sass",

// JSON BUILD SCRIPTS

    "compile:sass": "sass sass/main.scss css/style.comp.css",
    "concat:css": "concat -o css/style.concat.css css/icon-font.css css/style.comp.css",
    "prefix:css": "postcss --use autoprefixer -b 'last 10 versons' css/style.concat.css -o css/style.prefix.css",
    "compress:css": "sass css/style.prefix.css css/style.css --style compressed",
    "build:css": "npm-run-all compile:sass concat:css prefix:css compress:css"
