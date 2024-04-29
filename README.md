# bar128-love

**Barcode rendering library for LÖVE**, based on Zanstra's JS implementation ([code128.js](https://zanstra.com/my/Barcode/code128.js)).

## Installation

You can simply download the `bar128-love.lua` file from the [GitHub repository](https://github.com/Nawias/bar128-love) and include it in your LÖVE project.

## Usage

Here's an example of how to use the library in a LÖVE program:

```lua
local Barcode = require("bar128-love")

function love.load()
    -- Create a new Barcode object with the code "12345"
    barcode = Barcode("12345")
end

function love.draw()
    -- Draw the barcode at position (100, 100)
    barcode:draw('notext', 100, 100)
end
```

This example will render a barcode with the code "12345" at position (100, 100).

## Public Methods

### Constructor

```lua
Barcode(code: string|number, barHeight: number, barWidth: number, barcodeType: 'A'|'B'|'C'): Barcode
```

Creates a new Barcode object with the specified parameters:

- `code`: The text to be encoded in the barcode.
- `barHeight`: The height of the barcode image in pixels (default: 20).
- `barWidth`: The width of one bar in pixels (default: 1).
- `barcodeType`: The code 128 character set to use (`'A'`, `'B'` or `'C'`). If not provided, the library will detect the charset automatically.

### `draw(text: 'notext'|'text', x: number, y: number)`

Draws the barcode on the screen.

- `text`: ~~Indicates whether the text representation should be drawn underneath the barcode.~~ Coming Soon™.
- `x`: The X coordinate of the top-left corner of the barcode.
- `y`: The Y coordinate of the top-left corner of the barcode.

> ℹ️ Note that the X/Y position accounts for the initial 'quiet zone' of the barcode.

### Getters and Setters

#### `getCode(): string|number`

Returns the current barcode value.

#### `setCode(code: string|number, barcodeType: 'A'|'B'|'C')`

Changes the barcode's value.

- `code`: The new barcode value.
- `barcodeType`: (Optional) The code 128 character set to use (`'A'`, `'B'` or `'C'`). If not provided, the library will detect the charset automatically.
> ⚠️ Warning: changing the value causes the barcode to be re-parsed internally. Don't use this too often. 

#### `getBarWidth(): number`

Returns the current bar width.

#### `setBarWidth(width: number)`

Changes the base width of bars.

- `width`: The new bar width in pixels.

#### `getBarHeight(): number`

Returns the current barcode height.

#### `setBarHeight(height: number)`

Changes the barcode's height.

- `height`: The new barcode height in pixels.

## License

This library is licensed under the MIT License. See the [bar128.lua](https://github.com/Nawias/bar128-love/blob/main/bar128.lua) file for details.