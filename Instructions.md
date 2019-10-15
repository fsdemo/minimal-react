Creating a React App from Scratch.

Initialize as an NPM app
	npm init

Install Webpack
	npm install webpack webpack-cli webpack-dev-server --save-dev

Install Babel
	npm install 
		@babel/core 
		babel-loader 
		@babel/preset-env 
		@babel/preset-react 
		--save-dev
	
Configure Babel
	create a file called .babelrc
	
	{
		"presets" : ["@babel/preset-env","@babel/preset-react]
	}
	
Tell Webpack to use Babel as a preprocessor for Javascript (and JSX) files and config the dev server

	create a file webpack.config.js
	
	module.exports = {
		module: {
			rules: [
				{
					test: /\.(js|jsx)$/,
					exclude: /node_modules/,
					use: {
						loader: "babel-loader"
					}
				}
			]
		},
		devServer: {
			contentBase: path.join(__dirname,'public'),
			open:true
		}
	}
	
Install React

	npm install react react-dom
	
	
Create files to serve up

	public/index.html
	src/App.js
	src/index.js
		
Tie it all together now

	in package.json add the following scripts.
	
	"start": "webpack-dev-server --mode development",
    "build": "webpack --mode production"