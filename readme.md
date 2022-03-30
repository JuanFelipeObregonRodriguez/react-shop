**comandos para construir un react project paso a paso**

-primero ejecutamos el comando npm init, luego procedemos a instalar npm
con el comando npm install

-una vez que tengamos nuestros modulos de node, creamos la estructura inicial del proyecto,
para ello creamos dos carpetas, public y src, donde en src estarán anidadas las clases o componentes

-necesitamos configurar nuestro entorno de desarrollo, no obstante requerimos instalar webpack y babel.

webpack ` npm install webpack webpack-cli webpack-dev-server  `
babel ` npm install @babel/core @babel/preset-env @babel/preset-react `
HtmlPlugin ` npm install babel-loader html-loader html-webpack-plugin`

cuando tengamos instaladas nuestras dependencias vamos a prodecer a crear el archivo webpack.config y .babelrc. Dentro de nuestros archivos vamos a configurar el archivo webpack.config y .babelrc.

-en la carperta public agregamos nuestro html 

**comandos para instalar dependencias necesarias para la ejecucion del html**
npm install css-loader

npm install  -g sass

npm i mini-css-extract-plugin

 npm install style-loader --save

 **sass y preprocesadores**

 `npm i mini-css-extract-plugin css-loader style-loader sass sass-loader -D`

 en el archivo webpack.config.js se configura en el module rules el regex para que los archivos css y sass funcionen sin ningun problema

 **react-router-dom**

 ya que react está diseñado para hacer SPA(single page aplication) necesitamos una dependencia del mismo que nos permite cambiar entre hojas estaticas de forma dinamica.
-para instalar ejecutamos el comando `npm install react-router-dom`

despues importamos las propiedades de react-router-dom en nuestro archivo APP.jsx

`import {BrowserRouter, Route, Routes} from 'react-router-dom'` 

-elementos como botones o inputs deben ser componentes, para que los containers puedan reutilizarlos al máximo. Además de que así solo escribiremos sus estilos una vez.

**configuracion de las rutas de los archivos por medio de webpack**

- primero ubicamos la sección resolve en modules, en nuestro archivo webpack.config.js:

`resolve: {
		extensions: ['.js', '.jsx'],
	},`

- procedemos a agregar las rutas para acceder de una forma mas ordenada a las carpetas cuando importemos un elemento: 

`
resolve: {
		extensions: ['.js', '.jsx'],
	},`
    	alias:{
			'@components':path.resolve(__dirname, 'src/components/'),
			'@containers':path.resolve(__dirname, 'src/containers/'),
			'@styles':path.resolve(__dirname, 'src/styles/'),
			'@icons':path.resolve(__dirname, 'src/assets/icons/'),
			'@logos':path.resolve(__dirname,'src/assets/logos/')
			
		},
`