# Javascript Webpack asset management

Manage the asset of a project with webpack.

## Css

You can import the css file from a Javascript module.

1. Install `style-loader` and `css-loader`:
    > npm install --save-dev style-loader css-loader
2. Add rules in `webpack.config.js`:
    ```javascript
      module: {
        rules: [
          {
            test: /\.css$/i,
            use: ['style-loader', 'css-loader'],
          },
        ],
      },
    ```
3. Add a `style.css` in `/src`
4. you can add the css file in a js file with:
    > import "./style.css";

## Images

1. Add rules in `webpack.config.js`:
    ```javascript
      module: {
        rules: [
          {
            test: /\.(png|svg|jpg|jpeg|gif)$/i,
            type: 'asset/resource',
          },
        ],
      },
    
    ```
2. Add images in `/src`, for example `icon.png`
3. Import and use the images in js file:
    ```javascript
    import Icon from './icon.png';
    
    const myIcon = new Image();
    myIcon.src = Icon;
    
    document.appendChild(myIcon);
    ```

## Fonts

1. Add rules in `webpack.config.js`:
    ```javascript
      module: {
        rules: [
          {
            test: /\.(woff|woff2|eot|ttf|otf)$/i,
            type: 'asset/resource',
          },
        ],
      },
    ```
2. Add fonts in `/src`
3. Incorporate them with `@font-face` in css:
    ```css
    @font-face {
        font-family: 'MyFont';
        src: url('./my-font.woff2') format('woff2'),
         url('./my-font.woff') format('woff');
     font-weight: 600;
     font-style: normal;
    }
    
    div {
        font-family: 'MyFont';
    }
    ```
[source](https://webpack.js.org/guides/asset-management/)
