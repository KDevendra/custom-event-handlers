# Web Interaction Control Toolkit

Enhance user experience and bolster security in your web applications using the Web Interaction Control Toolkit. This toolkit provides easy-to-use JavaScript snippets that address various aspects of user interaction, preventing unwanted actions and ensuring a seamless and secure browsing experience.

## Features

### 1. Context Menu Control

Disable the context menu when right-clicking on the page to promote a controlled user interface.

```javascript
$(document).on("contextmenu", function () {
   return false;
});
```

### 2. User Selection Control

Prevent text selection across the entire page while selectively enabling it for input and textarea elements.

```javascript
$("body").css({
   "-webkit-user-select": "none",
   "-moz-user-select": "none",
   "-ms-user-select": "none",
   "user-select": "none",
});

$("input, textarea").css({
   "-webkit-user-select": "auto",
   "-moz-user-select": "auto",
   "-ms-user-select": "auto",
   "user-select": "auto",
});
```

### 3. Keyboard Shortcut Disabling

Disable specific keyboard shortcuts to maintain control over search and view source functionalities.

```javascript
$(document).on("keydown", function (event) {
   if ((event.ctrlKey || event.metaKey) && (event.keyCode === 70 || event.keyCode === 85)) {
      event.preventDefault();
   }
});
```

### 4. Copy Protection

Secure your content by disabling copying via right-click and keyboard shortcuts.

```javascript
document.addEventListener("keydown", function (event) {
   if ((event.ctrlKey || event.metaKey) && (event.keyCode === 67 || event.keyCode === 77)) {
      event.preventDefault();
   }
});

document.addEventListener("keydown", function (event) {
   if ((event.ctrlKey || event.metaKey) && event.shiftKey && (event.code === "KeyC" || event.code === "KeyM")) {
      event.preventDefault();
      event.stopPropagation();
   }
});
```

## Usage

1. Copy the desired snippet from the toolkit.
2. Integrate the snippet into your project's JavaScript file or script tag.

```html
<script src="your-script.js"></script>
```

3. Customize the snippets as needed for your application.

## Contribution

If you have suggestions, improvements, or encounter issues, feel free to contribute by opening issues or submitting pull requests. Together, let's build a more secure and user-friendly web!

## License

This toolkit is licensed under the [MIT License](LICENSE).
