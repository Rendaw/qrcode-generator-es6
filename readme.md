<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [qrcode-generator-es6](#qrcode-generator-es6)
    -   [How to use:](#how-to-use)
-   [qrcode](#qrcode)
    -   [isDark](#isdark)
    -   [getModuleCount](#getmodulecount)
    -   [make](#make)
    -   [createSvgTag](#createsvgtag)
    -   [createImgTag](#createimgtag)
-   [stringToBytesFuncs](#stringtobytesfuncs)
-   [stringToBytes](#stringtobytes)
-   [QRMode](#qrmode)
-   [QRErrorCorrectionLevel](#qrerrorcorrectionlevel)
-   [QRMaskPattern](#qrmaskpattern)

## qrcode-generator-es6

<table width="100%">
    <tr>
        <td>
            <a href="https://github.com/rendaw/qrcode-generator-es6"><img src="https://raw.githubusercontent.com/primer/octicons/master/lib/svg/mark-github.svg?sanitize=true"> Github</a>
        </td>
        <td>
            <a href="https://circleci.com/gh/rendaw/qrcode-generator-es6"><img alt="Build Status" src="https://circleci.com/gh/rendaw/qrcode-generator-es6.svg?style=svg"></a>
        </td>
</table>

### How to use:

First run:

    npm install --save qrcode-generator-es6

Then use it in your code like:

    import qrcode from 'qrcode-generator-es6';

    const qr = new qrcode(0, 'H');
    qr.addData('This is my data');
    qr.make();
    my_element.innerHTML = qr.createSvgTag({});

## qrcode

Displays a QR code. Set the code data with `addData` and, call `make` and then call `createSvgTag` or `createImgTag`.

See `gallery.html` for an example.

**Parameters**

-   `typeNumber` **integer** The minimum QR code type number from 1 to 40.  Using 0 allows any QR code type number.
-   `errorCorrectionLevel` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** 'L','M','Q','H'

### isDark

**Parameters**

-   `row`  
-   `col`  

Returns **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** true if the module at `row, col` is dark.

### getModuleCount

Returns **integer** The module count in one dimension of the QR code.  The total number of modules is the square of this value.

### make

Call this when done adding data before getting the generated QR code image.

### createSvgTag

**Parameters**

-   `args` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
    -   `args.drawCell` **[function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** A callback with arguments `column, row, x, y` to draw a cell.  `x, y` are the coordinates to draw it at.  `c, y` are the QR code module indexes.  Returns the svg element child string for the cell.
    -   `args.cellColor` **[function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)?** A callback which returns the color for the cell.  By default, a function that returns `black`.  Unused if `drawCell` is provided.
    -   `args.margin` **integer?** The margin to draw around the QR code, by number of cells.
    -   `args.obstruction` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)?** An image to place in the center of the QR code.
        -   `args.obstruction.width` **integer** Width of the obstruction as a percentage of QR code width.
        -   `args.obstruction.height` **integer** Height of the obstruction as a percentage of QR code height.
        -   `args.obstruction.path` **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The path of the obstruction image.
    -   `args.cellSize`  

Returns **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** An svg tag as a string.

### createImgTag

**Parameters**

-   `cellSize` **integer** The size of a module in pixels.
-   `margin` **integer** The margin to draw around the QR code in pixels.

Returns **[String](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** An img tag as a string.

## stringToBytesFuncs

## stringToBytes

## QRMode

## QRErrorCorrectionLevel

## QRMaskPattern
