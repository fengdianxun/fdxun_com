---
title: " react-native最简单的页面跳转\t\t"
url: 231.html
id: 231
comments: false
categories:
  - react-native
date: 2018-07-14 15:17:56
tags:
---

1.  加依赖
    
        npm install --save react-navigation
        
    
2.  新建导航页面 index.js 路由顺序很重要，第一个就是启动页面，其他的需要手动跳转. screnn的值就是需要跳转的页面
    

    import {
      createStackNavigator,
    } from 'react-navigation';
    
    import HomeScreen from '.HomeScreen;
    import ProfileScreen from '.ProfileScreen;
    
    const App = createStackNavigator({
      Home: { screen: HomeScreen },
      Profile: { screen: ProfileScreen },
    });
    
    export default App;
    

3.  入口页面注册导航页面

    import { AppRegistry } from 'react-native';
    import App from './app/index';
    
    AppRegistry.registerComponent('SuperKouSuan', () => App);
    
    

4.  页面跳转 跳转依赖路由名,datas为页面传参

    this.props.navigation.navigate('Profile',datas)
    

5.  页面接参 通过key值一个一个取,可以添取不到的默认值.

    let data = this.props.navigation.getParam("data","default");