- Using create-react-app with relay


    Refer https://www.prisma.io/blog/getting-started-with-relay-modern-46f8de6bd6ec/

    npm install -g create-react-app
    create-react-app instagram
    cd instagram
    yarn add react-relay
    yarn add relay-compiler babel-plugin-relay graphql --dev
    yarn eject

    Edit package.json

    "scripts": {
      "relay": "relay-compiler --src ./src --schema ./schema.graphql"
    },
    "babel": {
      "presets": [
        "react-app"
      ],
      "plugins": [
        "relay"
      ]
    },
