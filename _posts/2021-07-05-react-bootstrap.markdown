---
layout: post
title:      "React Boostrap"
date:       2021-06-26 12:31:43 -0400
permalink:  react_bootstrap
---

Prerequisites
To setup React web app in your system, you must have Node.js installed on your system. Avoid installing Node if you already have installed Node else follow this tutorial on how to install Node?

Verify whether Node js is installed or not in your machine by running the following command:

node -v

# v10.16.0
Bash
Setting up React Project
In this first step, we will create React project using create-react-app (CRA). Run the following command to create the basic React app.

npx create-react-app react-bootstrap-app
Bash
Get into the React directory:

cd react-bootstrap-app
Bash
Run command to start the React app.

npm start
Bash
Following will be the React project’s directory structure created by the command we used above.

├── node_modules
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robot.txt
├── src
│   ├── App.css
│   ├── App.js
│   ├── App.test.js
│   ├── index.css
│   ├── index.js
│   ├── logo.svg
│   └── serviceWorker.js
├── .gitignore
├── package-lock.json
├── package.json
├── README.md
Bash
Methods to Include Bootstrap 4 in React Application
There are various methods available through which we can implement Bootstrap with React application; some of the ways are given below:

Implement Bootstrap using CDN
Install Bootstrap NPM library from Node Package Manager.
Installing and Using React-Bootstrap library in React
Integrating Reactstrap Bootstrap library in React
In this tutorial, we’ll examine the above methods one by one.

Using Bootstrap Framework via CDN in React App
In this tutorial, we will check out how to implement Bootstrap from a CDN (content delivery network) in React app. This approach is straightforward and requires only <link rel="stylesheet" /> tag to be inserted in public/index.html file.

<link href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
Markup
Bootstrap 4 requires jQuery, Popper.js, and Bootstrap.js to be included in your project to make its JavaScript components work appropriately. Include following JavaScript files before the body tag ends in your index.html file in React app.

<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>

<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
Markup
Why Adding Bootstrap 4 via CDN in React is Not a Best Approach?
React works on Virtual DOM programming concept. In this approach, a virtual module of a user interface is kept in the memory. And combined together with Document Object Model with the help of ReactDOM. This process is known as reconciliation and known as “virtual DOM” approach in React.

Since Bootstrap 4 is entirely dependent on jQuery and Popper.js and using both of these libraries in React is not considered the best approach because of direct DOM manipulation behavior.

Setting up Bootstrap in React App Using NPM
We can also set up Bootstrap in React using NPM, in our React app. Enter the following command in the terminal and hit enter.

npm install bootstrap
Bash
Now, we have installed the bootstrap via NPM package. In the next step, we require to import Bootstrap CSS in our React project. Go to src/index.js file and include the following code.

import 'bootstrap/dist/css/bootstrap.min.css';
JavaScript
You are all set to use Bootstrap’s UI component in your React app. But If you want to use JavaScript components, you need to integrate jQuery and Popper.js packages using the following command.

npm install popper.js jquery
Bash
Head over to src/index.js file and include the given code.

import $ from 'jquery';
import Popper from 'popper.js';
import 'bootstrap/dist/js/bootstrap.bundle.min';
Bash
Finally, you can use Bootstrap UI and JavaScript components easily in your React app.

Using React-Bootstrap in React Project
React-Bootstrap is a popular front-end CSS framework, and this framework is exclusively re-built for React framework. It does not require to be included jQuery and Popper.js.

Follow this step by step MERN Stack CRUD App tutorial, and here I have used the React-Bootstrap framework and its various UI components to build the layout of a React app.

You will learn following things in the referred tutorial:

Install and set up React-Bootstrap in React app.
Working with grid system such as Container, Row and Col.
Getting started with Nav, Navbar, Forms, Buttons etc.
Adding reactstrap Library in React Project
The reactstrap is a well-known framework it offers Bootstrap 4 components to React. The reactstrap supports the latest version of Bootstrap. It allows React developers to use various Bootstrap components such as grid system, navigation, icons, typography, forms, buttons, and table.

Run command to install Bootstrap and reactstrap from NPM (node package manager). The reactstrap does not include Bootstrap CSS by default, we will install both the libraries separately.

npm install --save bootstrap
npm install --save reactstrap react react-dom
Bash
Next, we will include Bootstrap CSS in the src/index.js file.

import 'bootstrap/dist/css/bootstrap.min.css';
Bash
Now, we are all set to use reactstrap UI components in React app.

Using Reactstrap Buttons in React App
Let’s check out how we can use reactstrap buttons in React app. First, we have to import Buttons component in src/App.js file and include the Buttons code from reactstrap site.

import React from 'react';
import { Button } from 'reactstrap';
import './App.css';

function App() {
  return (
    <div className="App">
      <Button color="primary">primary</Button>{' '}
      <Button color="secondary">secondary</Button>{' '}
      <Button color="success">success</Button>{' '}
      <Button color="info">info</Button>{' '}
      <Button color="warning">warning</Button>{' '}
      <Button color="danger">danger</Button>{' '}
      <Button color="link">link</Button>
    </div>
  );
}

export default App;
React JSX
Reactstrap Navbar in React Project
In this step, we will learn how to use reactstrap navbar to create navigation in React project.

There is no other option than reactstrap navbar, to create responsive navigation bar in React app. It works flawlessly on every device type. The reactstrap navbar element includes many other small components such as Collapse, Navbar, NavbarToggler, Nav, NavItem, NavLink, DropDownMenu, etc.

As you can see, we are also imported Fragment in react. React Fragment groups a list of children without including extra nodes to the DOM.

Add the reactstrap navbar services in src/App.js file as mentioned below:

import React from 'react';
import { Fragment } from 'react';
import {
  Collapse,
  Navbar,
  NavbarToggler,
  NavbarBrand,
  Nav,
  NavItem,
  NavLink,
  UncontrolledDropdown,
  DropdownToggle,
  DropdownMenu,
  DropdownItem
} from 'reactstrap';

export default class App extends React.Component {

  constructor(props) {
    super(props);

    this.toggle = this.toggle.bind(this);
    this.state = {
      isOpen: false
    };
  }
  toggle() {
    this.setState({
      isOpen: !this.state.isOpen
    });
  }

  render() {
    return <Fragment>
      <Navbar color="light" light expand="md">
        <NavbarBrand href="/">reactstrap</NavbarBrand>
        <NavbarToggler onClick={this.toggle} />
        <Collapse isOpen={this.state.isOpen} navbar>
          <Nav className="ml-auto" navbar>
            <NavItem>
              <NavLink href="/components/">Components</NavLink>
            </NavItem>
            <NavItem>
              <NavLink href="https://github.com/reactstrap/reactstrap">GitHub</NavLink>
            </NavItem>
            <UncontrolledDropdown nav inNavbar>
              <DropdownToggle nav caret>
                Options
                </DropdownToggle>
              <DropdownMenu right>
                <DropdownItem>
                  Option 1
                  </DropdownItem>
                <DropdownItem>
                  Option 2
                  </DropdownItem>
                <DropdownItem divider />
                <DropdownItem>
                  Reset
                  </DropdownItem>
              </DropdownMenu>
            </UncontrolledDropdown>
          </Nav>
        </Collapse>
      </Navbar>
    </Fragment>
  }
}
React JSX
Now, you have created the responsive and intuitive Navigation bar in React app.

Implementing Reactstrap Modal in React
In this step, we will learn how to implement reactstrap modal in react app using reactstrap API.

import React from 'react';
import { Button, Modal, ModalHeader, ModalBody, ModalFooter } from 'reactstrap';

export default class App extends React.Component {

  constructor(props) {
    super(props);
    this.state = {
      modal: false
    };

    this.toggle = this.toggle.bind(this);
  }

  toggle() {
    this.setState(prevState => ({
      modal: !prevState.modal
    }));
  }

  render() {
    return (
      <div>
        <Button color="danger" onClick={this.toggle}>Open Modal</Button>
        <Modal isOpen={this.state.modal} toggle={this.toggle} className={this.props.className}>
          <ModalHeader toggle={this.toggle}>Modal title</ModalHeader>
          <ModalBody>
            A wonderful serenity has taken possession of my entire soul, like these sweet mornings of spring which I enjoy with my whole heart. I am alone, and feel the charm of existence in this spot, which was created for the bliss of souls like mine. I am so happy, my dear friend, so absorbed in the exquisite sense of mere tranquil existence, that I neglect my talents. I should be incapable of drawing a single stroke at the present moment; and yet I feel that I never was a greater artist than now. When, while the lovely valley teems with vapour around me, and the meridian sun strikes the upper surface of the impenetrable foliage of my trees, and but a few stray gleams steal into the inner sanctuary, I throw myself down among the tall grass by the trickling stream; and, as I lie close to the earth, a thousand unknown plants are noticed by me: when I hear the buzz of the little world among the stalks, and grow familiar with the countless indescribable forms of the insects and flies, then I feel the presence of the Almighty.
      </ModalBody>
          <ModalFooter>
            <Button color="primary" onClick={this.toggle}>CTA</Button>
            <Button color="secondary" onClick={this.toggle}>Cancel</Button>
          </ModalFooter>
        </Modal>
      </div>
    )
  }
}
React JSX
You can check out reactstrap model here API to make more customization in model elements.

Conclusion
Finally, we have completed the React Bootstrap 4 Tutorial. In this React tutorial, we learned various methods to use Bootstrap 4 in React project. We explore reactstrap, and it’s multiple UI and JavaScript components. I hope you liked this tutorial, please consider sharing this tutorial with others.
