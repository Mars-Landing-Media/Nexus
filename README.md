# Mars Landing Media LLC - Nexus Hosting Service: Host Anything!

**Developer**: Jon DeLuna  

## Description

The **Nexus Hosting Service** is a custom ServiceNow application developed by **Jon DeLuna** under **Mars Landing Media LLC**. This application transforms your ServiceNow instance into a fully functional web server. It enables you to host bespoke web applications that seamlessly integrate with ServiceNow data, leveraging RESTful endpoints to deliver HTML, CSS, and JavaScript. Supporting frameworks like Angular and ReactJS, this service allows dynamic, custom-built solutions independent of Service Portal or Workspace.

## Features

- **Framework Agnostic**: Supports popular frameworks like Angular, ReactJS, or any other front-end library.
- **Dynamic Data Hosting**: Serves HTML, CSS, and JavaScript files directly from your ServiceNow instance.
- **Independent Hosting**: Operates independently of Service Portal and Workspace, offering flexibility for custom applications.
- **Scalable and Modular**: Tailored for scalable, reusable web solutions directly within the ServiceNow ecosystem.
- **Located under the ALL menu**: After you install this app, you can begin updating the table by going to 'All -> Nexus Hosting Services'

## How It Works

The **Nexus Hosting Service** operates as a web server embedded within your ServiceNow instance. Developers can use its REST endpoints to serve HTML, CSS, and JavaScript resources. These resources can then be used to host dynamic, custom-built web applications.

## Setting Up Content in the Nexus Table

When creating records in the Nexus Hosting Service table, you need to define the `path` field to correctly reference your hosted resources. For this example:

- **CSS File**: Create a record with the `path` value set to `marslandingmedia_css`.
- **HTML File**: Create a record with the `path` value set to `marslandingmedia`.

These paths will allow the REST API to correctly serve the corresponding files.

### Example Table Configuration

| Field         | CSS Record                  | HTML Record                |
|---------------|-----------------------------|----------------------------|
| `Path`        | `marslandingmedia_css`      | `marslandingmedia`         |
| `Content`     | CSS content (example below) | HTML content (example below) |
| `MIME Type`   | `text/css`                  | `text/html`                |
| `Active`      | `true`                      | `true`                     |

## Example Configuration and Usage

### Example URL to Access Hosted Page

Replace `<your-instance>` with your ServiceNow instance domain in the following URLs:

- **HTML File**:
https://<your-instance>.service-now.com/api/x_marsl_nexus/appserv/route?marslandingmedia

- **CSS**:  
https://<your-instance>.service-now.com/api/x_marsl_nexus/appserv/route?marslandingmedia_css


### Hosted HTML Example

Below is an example of an HTML page hosted through the Nexus Hosting Service.

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" type="text/css" href="https://<your-instance>.service-now.com/api/x_marsl_nexus/appserv/route?marslandingmedia_css">
</head>
<body>
  <div id="header">
      <svg width="64" height="64" viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" fill="#000000">
          <!-- SVG content -->
      </svg>
      <h1>Nexus Hosting Service</h1>
      <h3>Mars Landing Media LLC</h3>
  </div>

  <div id="content">
      <div id="message">
          The Nexus Hosting Service transforms your ServiceNow instance into a dynamic web server, 
          enabling you to host bespoke applications built with frameworks like Angular or ReactJS. 
          It provides RESTful endpoints to seamlessly interact with instance data and create fully customized 
          and dynamic web experiences independent of Service Portal or Workspace.
      </div>
  </div>
</body>
</html>
```

### Hosted HTML Example (ReactJS & Material UI Button)

Below is an example of an HTML page with a ReactJS button component hosted through the Nexus Hosting Service.

```html
<!DOCTYPE html>
<html>
<head>

        <link rel="stylesheet" type="text/css" href="/api/x_marsl_nexus/appserv/route?marslandingmedia.css">

       <!-- Material Design -->
       <link href="https://unpkg.com/material-components-web@latest/dist/material-components-web.min.css" rel="stylesheet">
       <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons"> 


</head>
<body>
    <div id="header">
        <svg width="64" height="64" viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" fill="#000000">
          <!-- SVG content -->
        </svg>

        <h1>Nexus Hosting Service</h1>
        <h3>Mars Landing Media LLC</h3>
    </div>

    <div id="content">
        <div id="message">
            The Nexus Hosting Service transforms your ServiceNow instance into a dynamic web server, 
            enabling you to host bespoke applications built with frameworks like Angular or ReactJS. 
            By wiring up your own RESTful CRUD operations, you can seamlessly interact with instance data, 
            creating fully customized and dynamic web experiences independent of Service Portal or Workspace.
        </div>

      <div>
    </div>


<button class="mdc-button mdc-button--raised">
  <span id="like_container" class="mdc-button__label">Like Button</span>
</button>


  <!-- Load React. -->
   <script src="/api/x_marsl_nexus/appserv/route?react.production.min.js" crossorigin></script>
   <script src="/api/x_marsl_nexus/appserv/route?react-dom.production.min.js" crossorigin></script> 
  
  <!-- Load our React component. -->
  <script src="/api/x_marsl_nexus/appserv/route?likeContainer.js" crossorigin></script>



<!-- Load Material UI -->
<script src="https://unpkg.com/material-components-web@latest/dist/material-components-web.min.js"></script>

</body>
</html>

```


### Hosted CSS Example

Below is an example of a CSS file to style the hosted HTML page.

```css
/* General body styling */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background-color: #f4f4f4;
}

/* Header section */
#header {
    width: 60%; /* Constrain width for book-like appearance */
    text-align: center;
    margin-bottom: 20px;
}

#header h1 {
    font-size: 3rem; /* Larger font for the application name */
    color: #333;
    margin: 10px 0;
}

#header h3 {
    font-size: 1.5rem; /* Smaller font for the Mars Landing Media name */
    color: #555;
    margin: 5px 0;
}

/* SVG icon styling */
svg {
    margin-bottom: 10px;
}

/* Content section */
#content {
    width: 60%; /* Constrain content to a readable width */
    text-align: justify; /* Align text like a book */
    background-color: #fff; /* Optional: Add a background for content area */
    padding: 20px; /* Add padding for spacing */
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1); /* Optional: Subtle shadow for book effect */
    border-radius: 8px; /* Optional: Rounded corners for softer look */
}

#message {
    font-size: 1.2rem;
    color: #555;
    line-height: 1.6; /* Improve readability with proper line spacing */
}
```

### Hosted ReactJS Button Component

Below is an example of a ReactJS button. In the HTML example above I have styled it with Material UI.

```javascript

'use strict';

const e = React.createElement;

class likeText extends React.Component {

  constructor(props) {
    super(props);
    this.state = { liked: false };
  }

  render() {    
    if (this.state.liked) {
      return 'You liked this ReactJS button';
    }

    return e(
      'span',
      { onClick: () => this.setState({ liked: true }) },       
      'ReactJS Button'
    );
  }
  
}


const domContainer = document.querySelector('#like_container');
const root = ReactDOM.createRoot(domContainer);
root.render(e(likeText));

```


