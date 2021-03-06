# BootstrapSidebar
> Bootstrap Sidebar Component for Vue 2.x. Based on this [tutorial](https://bootstrapious.com/p/bootstrap-sidebar) by Bootstrapious.com

## Install

``` bash
    npm install b-sidebar --save
```

## Usage

*1\. Import the component*

```
import BootstrapSideBar from 'b-sidebar';
```

*2\.1 Use it globally*

```
Vue.use(BootstrapSideBar);
```

*2\.2 Or use it locally*

```
components: {
    BootstrapSideBar
},
```

*3\. Update your app or template:*
```
<div>
...
<BootstrapSideBar :sidenavConfig="sidenavConfig" :header="header" :hasNavbar="hasNavbar" :links="sidelinks" :navs="headerLinks">
    <router-view/>
</BootstrapSideBar>
...
</div>
```

*4\. main.js or main.ts file changes:*
You have to import jquery in order to work with smooth transition.

```
import jquery from 'jquery';
(window as any).$ = (window as any).jQuery = jquery; //If you have typescript based implementation(main.ts)
window.$ = window.jQuery = jquery; //If you have normal javascript file (main.js)
import 'bootstrap';
```
You can import anything after above line.
## Properties

`sidenavConfig`: `{type: Object}` - Global Configuration to be done on sidenav. Object will have following properties : 
    { `sidenavMainColor` : `{type: String}` = provide color from given options on [bootstrap](https://getbootstrap.com/docs/4.0/components/navbar/#color-schemes) , 
      `sidenavBgColor` : `{type: String}` = provide text-color combination to show up well from given options(eg. navbar-light,navbar-dark) on [bootstrap](https://getbootstrap.com/docs/4.0/components/navbar/#color-schemes), 
      `navbarClass` : `{type: String}` = Your custom class to give style you want to navbar, `sidenavClass` : Your custom class to give style you want to sidenav }

`header`: `{type: Object}` - provide this object if you want to have header in navbar. Object will contain properties with following names : `title` : Title to be shown as header, `href` : route where you want redirection on click of header.

`hasNavbar`: `{type: Boolean}` (Whether you want navbar to be shown or not, by default it will be `false`),
            
`sidelinks`: `{type: Array}` - Array of links to display in sidebar. Each array item is an Object that has the following properties: `label`, `href`, `icon`, `class` and `links` (for nested links),

`headerLinks`: `{type: Array}`: - Array of links to display in navbar. Each array item is an Object that has the following properties: `label`, `href`, `icon`, `class` and `navs` (for nested links).

## Contributing
Contributions and PRs are welcome. 

## Build Setup

``` bash

# build for production
npm run build
```

## What upcoming release will contain

Sidenav will have multi level menu items.
Sidenav menu items will have `class` arguement to give custom class to every menu item.