# Ignite Teams

## Path Mapping / short imports
````
yarn add babel-plugin-module-resolver -D
````
babel.config.js:
`````
module.exports = function (api) {
  api.cache(true);
  return {
    presets: ['babel-preset-expo'],
    plugins: [
      [
        'module-resolver',
        {
          root: ['./src'],
          alias: {
            '@assets': './src/assets',
            '@components': './src/components',
            '@routes': './src/routes',
            '@screens': './src/screens',
            '@storage': './src/storage',
            '@theme': './src/theme',
            '@utils': './src/utils',
          },
        },
      ],
    ],
  };
};


`````
tsconfig.json:
`````
{
  "extends": "expo/tsconfig.base",
  "compilerOptions": {
    "strict": true,
    "baseUrl": "./",
    "paths": {
      "@assets/*": ["./src/assets/*"],
      "@components/*": ["./src/components/*"],
      "@routes/*": ["./src/routes/*"],
      "@screens/*": ["./src/screens/*"],
      "@storage/*": ["./src/storage/*"],
      "@theme/*": ["./src/theme/*"],
      "@utils/*": ["./src/utils/*"],    }
  }
}

`````
App.tsx:
````
import Groups from '@screens/Groups';
````



