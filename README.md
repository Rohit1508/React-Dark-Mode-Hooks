This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `Dark Mode Implementation`

* Create `dark-theme.css` and `light-theme.css` files, add color variables required for entire web app, always use the same color variables for styling.
```
html[data-theme="dark"]  {
  --color: rgb(250, 250, 250);
  --background-color: rgb(5, 5, 5);
}
```

* Create a component `DarkModeToggle`, you will find the component in `DarkMode` folder.
... we are using react hooks and localStorage to implement this component.
```javascript
 const toggleThemeChange = () => {;
    if (checked === false) {
      localStorage.setItem("theme", "dark");
      document
        .getElementsByTagName("HTML")[0]
        .setAttribute("data-theme", localStorage.getItem("theme"));
      setChecked(true);
    } else {
      localStorage.setItem("theme", "light");
      document
        .getElementsByTagName("HTML")[0]
        .setAttribute("data-theme", localStorage.getItem("theme"));
      setChecked(false);
    }
  }
```
By clicking on toggle button we need to set the localStorage atribute `theme` as `light` or `dark`, simultaneously update the HTML attribute `data-theme` same as localStorage.
localStorage we are using to remember the choice of theme for a user for a web app.
