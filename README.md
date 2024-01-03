Blank Sass Layout

// NPM COMMANDS

    npm init
    npm install sass npm-run-all concat postcss-cli autoprefixer --save-dev
    npm install live-server -g
    npm run start
    ... develop project ...
    npm run build:css

// JSON DEV SCRIPTS

    "watch:sass": "sass sass/main.scss css/style.css -w",
    "devserver": "live-server",
    "start": "npm-run-all --parallel devserver watch:sass",

// JSON BUILD SCRIPTS

    "compile:sass": "sass sass/main.scss css/style.comp.css",
    "concat:css": "concat -o css/style.concat.css css/FILE-TO-CONCAT.css css/style.comp.css",
    "prefix:css": "postcss --use autoprefixer -b 'last 10 versons' css/FILE-TO-CONCAT.css.css -o css/style.prefix.css",
    "compress:css": "sass css/style.prefix.css css/style.css --style compressed",
    "build:css": "npm-run-all compile:sass concat:css prefix:css compress:css"

// JSON DevDependencies

    "autoprefixer": "^10.4.16",
    "concat": "^1.0.3",
    "npm-run-all": "^4.1.5",
    "postcss-cli": "^11.0.0",
    "sass": "^1.69.5"
