# webpack instructions
make directory (git clone)
npm init --y
npm install webpack webpack-cli --save-dev
create src and dist folder (index.js goes inside src folder)

create webpack.config.js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
module.exports = {
  entry: './src/index.js',
  output: {
    filename: '[name].bundle.js',
    path: path.resolve(__dirname, 'dist'),
    clean: true,
  },
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      },
      {
        test: /\.(png|svg|jpg|jpeg|gif)$/i,
        type: 'asset/resource',
      },
      {
        test: /\.(woff|woff2|eot|ttf|otf)$/i,
        type: 'asset/resource',
      },
    ],
  },
    plugins: [
    new HtmlWebpackPlugin({
      title: '',
    }),
  ],
};
npx webpack --config webpack.config.js

loading css
npm install --save-dev style-loader css-loader
add style.css to src folder

example of family font:
@font-face {
  font-family: 'MyFont';
  src: url('./my-font.woff2') format('woff2'),
    url('./my-font.woff') format('woff');
  font-weight: 600;
  font-style: normal;
}
npm install --save-dev csv-loader xml-loader

html webpack plugin
npm install --save-dev html-webpack-plugin
