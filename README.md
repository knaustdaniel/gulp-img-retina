# gulp-img-retina
add img attribute 'srcset' for retina

## Prerequisites
You must have a 2x image in the folder which the original image in.

## Install

`npm install gulp-img-retina`

## Usage

``` js
var gulp = require('gulp');
var imgRetina = require('gulp-img-retina');

var retinaOpts = {
    // Your options here.
};

gulp.task('views', function() {

  return gulp.src('./views/**/*.html')
    .pipe(imgRetina(retinaOpts))
    .on('error', function(e) {
      console.log(e.message);
    })
    .pipe(gulp.dest('./build'));

});
```

You put html in:
``` html
<figure>
	<img src="images/default/example.jpg" alt="example image" />
</figure>
```

And get html out:
``` html
<figure>
	<img src="images/default/example.jpg" alt="example image" srcset="images/default/example.jpg 1x, images/default/example@2x.jpg 2x" />
</figure>
```

## Options (Optional)

### options.suffix
Type: ```Object```

Default: ```{1: '', 2: '@2x'}```

The suffix will insert to image's path, the key is resolution, and value is suffix.
