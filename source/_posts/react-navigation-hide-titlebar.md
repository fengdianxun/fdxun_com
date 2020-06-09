---
title: " react-navigation hide titlebar\t\t"
url: 229.html
id: 229
comments: false
categories:
  - react-native
date: 2018-07-14 15:19:55
tags:
---

最关键的就是这句话，也就是路由可以设置一些属性。

    navigationOptions: {header: null}
    

    import {
        createStackNavigator,
    } from 'react-navigation';
    
    import Playing from './playing/index';
    
    const App = createStackNavigator({
        Home: {screen: Playing, navigationOptions: {header: null}},
        // Profile: { screen: ProfileScreen },
    });
    
    export default App;