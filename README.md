# README

      // CLI
      - rails new <app_name> --database=postgresql --skip-turbolinks
      - npm init --yes
      - npm install --save webpack react react-dom babel-core babel-loader babel-preset-es2015 babel-preset-react redux react-redux react-router lodash redux-thunk

#### added gems to GemFile
  - gem 'better_errors'
  - gem 'binding_of_caller'
  - gem 'pry-rails'
  - gem 'annotate'

        // CLI
        - bundle install

#### webpack
some minor changes due to webpack update to 2.2.1:

    //webpack.config.js
    var path = require("path");

    module.exports = {
      context: __dirname,
      entry: "./frontend/entry.jsx",
      output: {
        path: path.join(__dirname, 'app', 'assets', 'javascripts'),
        filename: "bundle.js"
      },
        module: {
        loaders: [
          {
            test: [/\.jsx?$/, /\.js?$/],
            exclude: /(node_modules|bower_components)/,
            loader: 'babel-loader',
            query: {
              presets: ['es2015', 'react']
            }
          }
        ]
      },
      devtool: 'source-maps',
      resolve: {
        extensions: ["*", ".js", ".jsx" ]
      }
    };



#### Entry file

      // frontend/entry.jsx

      import React from 'react';
      import ReactDOM from 'react-dom';

      document.addEventListener('DOMContentLoaded', () => {
          const root = document.getElementById('root');
          ReactDOM.render(<h1>Welcome to BenchBnB</h1>, root);
      });

#### Routing
      // CLI
      - rails g controller StaticPages

Set up a StaticPagesController with a root view containing a tag with the id "root". Update your routes.rb file to root to static_pages#root

      // CLI
      - rake db:create
      - webpack --watch
      - rails s (need to make sure that postgres is running)
