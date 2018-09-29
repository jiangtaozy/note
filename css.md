- Vertical alignment of an inline or table-cell box

      vertical-align: middle;

- CSS text-transform Property, No capitalization

      text-transform: none;

- Center Vertically

      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);

- Center Horizontally

      display: block;
      margin-left: auto;
      margin-right: auto;

- Config react CSS Modules

      // webpack.config.js
      rules: [
        // Whatever other rules you have here...
        {
          test: /\.less$/,
          use: [
            {
              loader: "style-loader"
            },
            {
              loader: "css-loader",
              options: {
                sourceMap: true,
                modules: true,
                localIdentName: "[local]___[hash:base64:5]"
              }
            },
            {
              loader: "less-loader"
            }
          ]
        }
      ]
      // Rest of your webpack.config.js

      // Header.js
      import React from "react";
      import style from "./sample.less";
      const Header = () => (
        <React.Fragment>
          <div className={style.header}>My Header Text</div>
        </React.Fragment>
      );
      export default Header;

- Image object-fit

    contain | cover | fill | none | scale-down

- One line text

    white-space: nowrap;
