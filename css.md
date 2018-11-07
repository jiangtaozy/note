- Vertical alignment of an inline or table-cell box

      vertical-align: middle;

- CSS text-transform Property, No capitalization

      text-transform: none;

- Center Vertically

      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);

      // or
      display: 'flex',
      flexDirection: 'column',
      alignItems: 'center',
      justifyContent: 'center',

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

- Black color

    rgba(0, 0, 0, 0.5)

- Img border-radius

    border-radius: 8px;

- flex-grow 属性

    // 如果我们希望，输入框占据当前行的所有剩余宽度，
    // 只需要指定输入框的flex-grow属性为1。
    // flex-grow属性默认等于0，即使用本来的宽度，不拉伸。
    // 等于1时，就表示该项目宽度拉伸，占据当前行的所有剩余宽度。

    input  {
      flex-grow: 1;
    }
