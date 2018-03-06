### SCSS Trump Maker

It takes a map of `key: value` or list and generates a set of **trump** classes.

#### Install
  - `npm i -S scss-mixin-trump-maker`
  - include into your SCSS code
    ```scss
    @import "~scss-mixin-trump-maker/index";
    ```

#### Usage

##### Parameters
  - $vairations `(map|list)`
  - $name `(string)`
  - $props... `(unlimited strings)`

##### Examples

  - Use it to generate spacing trumps:
    ```scss
    $spaces: (
      0: 0,
      1: 0.25rem,
      2: 0.5rem
    );

    @include trumps-maker($spaces, 'm', 'margin');
    @include trumps-maker($spaces, 'mt', 'margin-top');
    @include trumps-maker($spaces, 'my', 'margin-top', 'margin-bottom');
    @include trumps-maker($spaces, 'pr', 'padding-right');
    ```

    It will generate:
    ```css
    .m-0 {margin: 0 !important;}
    .m-1 {margin: 0.25rem !important;}
    .m-2 {margin: 0.5rem !important;}

    .mt-0 {margin-top: 0 !important;}
    .mt-1 {margin-top: 0.25rem !important;}
    .mt-2 {margin-top: 0.5rem !important;}

    .my-0 {margin-top: 0 !important; margin-bottom: 0 !important;}
    .my-1 {margin-top: 0.25rem !important; margin-bottom: 0.25rem !important;}
    .my-2 {margin-top: 0.5rem !important; margin-bottom: 0.5rem !important;}

    .pr-0 {padding-right: 0 !important;}
    .pr-1 {padding-right: 0.25rem !important;}
    .pr-2 {padding-right: 0.5rem !important;}
    ```

  - Use it to generate height trumps:
    ```scss
    $heights: (
      1: 25vh,
      2: 50vh,
      3: 75vh,
      4: 100vh
    );

    @include trumps-maker($heights, 'h', 'height');
    ```

    It will generate:
    ```css
    .h-1 {height: 25vh !important;}
    .h-2 {height: 50vh !important;}
    .h-3 {height: 75vh !important;}
    .h-4 {height: 100vh !important;}
    ```

  - Use it to primitive height trumps:
    ```scss
    $alignments: (
      right,
      center,
      left
    );

    @include trumps-maker($alignments, 'text', 'text-align');
    ```

    It will generate:
    ```css
    .text-right {text-align: right !important;}
    .text-center {text-align: center !important;}
    .text-left {text-align: left !important;}
    ```
