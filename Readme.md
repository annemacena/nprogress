NProgress-X ~~2.0✨~~
===========

This is just a fork from [Sílvia Mur](https://github.com/pchiwan)'s refactored tool ([real NProgress-X](https://github.com/pchiwan/nprogress)). That refactored tool was based on [Rico Sta. Cruz](https://github.com/rstacruz)'s [NProgress](https://github.com/rstacruz/nprogress).

So, if you want to know how use it, you should check out the installation and configuration [here](http://silvia.murblan.ch/nprogress/) 😉.

# But what's new? 🙄

Well, I was using that tool on project at my work and we were need to use some silly things like a spinner ![spinner](https://s15.postimg.cc/3oiiocc1n/Rolling-1s-20px.gif), a overlay effect and a setting to put some CSS class.

### New settings

- `barSelector`
    -  Set HTML attribute name and value to indicates the bar element  *(default: '[role="bar"]')*. 
- `spinnerSelector`
    -  Set HTML attribute name and value to indicates the spinner element  *(default: '[role="spinner"]')*. 
- `overlaySelector`
    -  Set HTML attribute name and value to indicates the overlay element  *(default: '[role="overlay-np"]')*. 
- `showOverlay`
    -  Set to true to turn on the overlay *(default: false)*. 
- `customClass`
    -  Used to set up a CSS class on nprogress element *(default: empty string)*. 

# What we did to work well
Basically, we work with a main bar (on top of body element) and with others bars in HTML elements.
The main bar was implemented like this:
```
const Nprogress = new NProgress({
    customClass: "np-master",
    showOverlay: true
})
```
So, we assume if the nprogress element has as container the HTML element 'body', it will be the main bar.

In others elements we just override the initial configuration with a selector of a specific element:
```
var c1 = new NProgress({ container: "#column1" });
```

