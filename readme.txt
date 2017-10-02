1. Install NodeJS: https://nodejs.org/en/
- link: https://nodejs.org/dist/v8.5.0/node-v8.5.0-x64.msi
- After install nodejs, check: node -v and npm -v
2. Install gulp
- npm i gulp -g
- npm i gulp --save
3. Install browser sync: https://www.browsersync.io/
- npm install -g browser-sync
- npm i browser-sync --save
4. Change to project directory. Create file: gulpfile.js. (Maybe use Visual Studio Code to create).

var gulp = require('gulp');
var browserSync = require('browser-sync');

var reload = browserSync.reload;

gulp.task('default', [], function() {
    console.log('Command:\n     serve - run live reload server');
});

gulp.task('serve', [], function() {
    browserSync({
        notify: false,
        server: {
            baseDir: '.'
        }
    });

    gulp.watch(['*.html'], reload);
});

5. Open Command Prompt (PowerShell) at the project directory, run command:
- gulp serve