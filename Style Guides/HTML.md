# HTML Style Guide

## Overview
This document describes the best practices and corporate standards for HTML. It is intended for all software developer employees. 

## Goals for Standardizing HTML
* Ensure safety, security, and reliability for all products and stakeholders, including customers. 
* Improve the code’s readability and sustainability.
* Make it easier for developers to maintain code quality, switch between tasks, and work together across teams.

## 1. General Coding Rules

### 1.1 Formatting
* Always use lowercase tag names.
* Each nested tag must be intended **once** inside of its parent tag.
* Place a line break after every block element.

#### 1.1.1 Example 
![Screenshot of a block of HTML code following proper formatting and functionality rules.](https://github.com/Mporter11/My-Writing/blob/main/Style%20Guides/Screenshots/Format_example.png)

### 1.2 Functionality
* Use a Javascript file if Javascript events are included. Do not use inline Javascript events or logic within the HTML. This increases the chance for errors when multiple languages are merged.
* Use CSS to style when coding for different types of devices. Do not create different versions of the HTML code. This makes the code difficult to maintain.
* Place images that are important to the content in-line with alt text to ensure they are referenced correctly. Images solely for presentation or design purposes may be better suited as CSS backgrounds.

### 1.3 Attributes
* Order the attributes with the format: id-> class -> tag attributes -> custom attributes
    <br><br>Example:
    ```
    <a href="/" data-controller="main" data-event="click">Text/a>
    ```
* Start custom attributes with the “data-” prefix
  <br><br>Example:
  ```
  <a href=”/” data-controller=”main” data-event=”click”>Text/a>
  ```

  ### 1.4 Semantics

  #### 1.4.1 What is semantic HTML?
  Semantic HTML is the use of HTML tags that convery the meaning (or semantic) of the content contained within them to both the web browser and the developer.

  #### 1.4.2 Why use semantic HTML?
  * Adding HTML tags provide additional information that define the roles and priority of the different parts of a webpage.
  * The tags make the overall code more comprehensible and useable for developers.
  * Provides a better use experience for the end user by improving how accessible, readable, and searchable web elements are.
 
  #### 1.4.3 Commonly used tags definitions
  * section: Used as the most generic of all sectioning elements. Always include a heading. 
  * article: Content that makes sense on its own (e.g. blog post, newsletter article).
  * aside: Used for content that is seperate, but related to the parent content.
  * div: Used for block level elements that usually make up the page structure.
  * span: Used for inline level elements.
 
  ## 2. Creating a New Document Rules

  ### 2.1 Design Process
  Follow this process when designing a new HTML document from scratch:
  1. Aim for reusable components where possible. Writing less code and reusing existing code can save time and effort, while using the same code for similar elements or features can help to ensure consistency and quality in the future.
  2. Brainstorm ideas by sketching on paper and collaborating with other developers.
  3. Focus on the content to select the most applicable HTML tags.

  ### 2.2 Setup Rules
  Follow this process when coding a new HTML document:
  1. Declare doctype and HTML element.
  2. Put the HEAD with the appropriate metadata.
  3. Add content to the body.

  #### 2.2.1 Example
 ![Screenshot of a block of HTML code following the rules for setting up a new HTML document.](https://github.com/Mporter11/My-Writing/blob/main/Style%20Guides/Screenshots/new_HTML_doc.png)
