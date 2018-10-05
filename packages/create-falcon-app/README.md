# Create Falcon App

This CLI tool helps you to create your application based on [DEITY Falcon](https://github.com/deity-io/falcon) with just one command.

### TL;DR

Generate your app with:
`npx create-falcon-app my-app`

then run the server in one terminal:
```bash
cd my-app/server
npm start
```
and the client in the second terminal:
```bash
cd my-app/client
npm start
```
then open http://localhost:3000 in your browser


## Longer version
You can use either npx (installed with npm) or yarn to generate the application. 

If you prefer npx use the following command:
```bash
npx create-falcon-app my-app
```

and if you prefer yarn use `yarn create` with the following syntax (notice space between `create` and `falcon-app`:
```bash
yarn create falcon-app my-app
```

That command will create folder `my-app` with 2 folders inside: 
```
my-app/
 |- server
 |- client
```

Folder `server` contains server which is responsible for communication with external APIs and services.
Server `client` contains service responsible for front-end part of the application.

Once `npx create-falcon-app my-app` or `yarn create falcon-app my-app` is done you can start both services. In one terminal window run the following commands to start the server part:
```bash
cd my-app/server
npm start # or yarn start
```
in the second terminal run the following commands to start the client part:
```bash
yarn create falcon-app my-app
cd my-app
yarn start
```


## Selecting the template for your project during generation.
Currently we provide just one template for the generator which delivers basic features of shop and blog (the template itself is called [shop-with-blog](https://github.com/deity-io/falcon/tree/master/examples/shop-with-blog).

In the future we'll provide more templates that can be selected with `--example` option. Full command that uses `shop-with-blog`  in that case will be as following:
```bash
npx create-falcon-app --example shop-with-blog my-app
```

## Using your backend services
By default `shop-with-blog` example uses demo Magento 2 and WordPress servers delivered by DEITY so you can check how DEITY Falcon works. If you cannot start the server part (from server folder) or you see any problems with server behavior please contact us via our [community slack channel](https://slack.deity.io). 

If you want to connect the generated app to your own Magento 2 backend you will need to install [Falcon Magento2 module](https://github.com/deity-io/falcon-magento2-module) which delivers REST endpoints required by DEITY Falcon and change configuration file (placed in `server/config/default.json`) to point the application to the correct url.

Also if you want to connect DEITY Falcon app to your WordPress server you'll have to to install [Falcon WordPress module](https://github.com/deity-io/falcon-wordpress-module) and also change configuration file (`server/config/default.json`) to point the application to the correct server.
