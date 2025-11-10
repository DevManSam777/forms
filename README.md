# @devmansam/forms

Professional, highly customizable web form components built as native Web Components.

![Web Inquiry Form](assets/form1.png)
![Minimalist Contact Form](assets/light.png)

## Overview

This package provides two production-ready form components that you can drop into any website with zero configuration. Both forms are built as Web Components, meaning they work everywhere - vanilla JavaScript, React, Vue, Angular, or any other framework.

### What's Included

**Web Inquiry Form** - A comprehensive multi-step form perfect for agencies, freelancers, or businesses collecting detailed client information. Features 5 steps covering personal info, business details, address, service selection, and a review page.

**Minimalist Contact Form** - A simple, elegant 3-field contact form (name, email, message) ideal for portfolios, landing pages, or anywhere you need a quick contact option.

### Why Use These Forms?

- **Drop-in Ready** - Add one line of code and you have a working, styled form
- **Zero Dependencies** - No jQuery, no framework requirements, just pure JavaScript
- **Fully Customizable** - Every color, font, and style can be customized via HTML attributes
- **Dark Mode Built-in** - Automatic detection with customizable dark theme colors
- **Mobile Responsive** - Works perfectly on phones, tablets, and desktops
- **Production Tested** - Used in real projects by DevLeads and portfolio sites

## Installation

### CDN

Add the script tag to your HTML:

```html
<!-- For the full Web Inquiry Form -->
<script src="https://cdn.jsdelivr.net/gh/DevManSam777/forms@latest/web-inquiry-form.js" defer></script>

<!-- For the Minimalist Contact Form -->
<script src="https://cdn.jsdelivr.net/gh/DevManSam777/forms@latest/contact-form.js" defer></script>

<!-- Or include both -->
<script src="https://cdn.jsdelivr.net/gh/DevManSam777/forms@latest/web-inquiry-form.js" defer></script>
<script src="https://cdn.jsdelivr.net/gh/DevManSam777/forms@latest/contact-form.js" defer></script>
```

### npm with Bundler

Install the package:

```bash
npm install @devmansam/forms
```

Import in your JavaScript:

```javascript
// Import both forms
import '@devmansam/forms';

// Or import individually
import '@devmansam/forms/web-inquiry-form';
import '@devmansam/forms/contact-form';
```

### npm without Bundler

Install the package:

```bash
npm install @devmansam/forms
```

Use with import maps in your HTML:

```html
<script type="importmap">
{
  "imports": {
    "@devmansam/forms": "./node_modules/@devmansam/forms/index.js",
    "@devmansam/forms/web-inquiry-form": "./node_modules/@devmansam/forms/web-inquiry-form.js",
    "@devmansam/forms/contact-form": "./node_modules/@devmansam/forms/contact-form.js"
  }
}
</script>

<script type="module">
  import '@devmansam/forms';
</script>
```

---

## Web Inquiry Form

A comprehensive multi-step form for collecting detailed client information including personal details, business information, address, and service preferences.

![Web Inquiry Form Steps](assets/form2.png)

### Basic Usage

```html
<web-inquiry-form
  api-url="https://your-api-endpoint.com/api/leads"
  form-title="Contact Us"
></web-inquiry-form>
```

### Features

- Multi-step progress indicator with 5 steps
- Personal information (name, email, phone)
- Business information (optional)
- Billing address collection
- Service selection
- Review step before submission
- Built-in field validation
- Phone number formatting

### Customization Attributes

#### Basic Configuration

| Attribute | Description | Default |
|-----------|-------------|---------|
| `api-url` | API endpoint URL | `http://localhost:5000/api/leads` |
| `theme` | Force theme: "light", "dark", or auto | Auto-detect |
| `form-title` | Form header text | "Web Development Inquiry" |

#### Layout & Typography

| Attribute | Description | Default |
|-----------|-------------|---------|
| `border-radius` | Corner roundness | `6px` |
| `font-family` | Custom font family | System fonts |
| `font-size` | Base font size | `16px` |
| `google-font` | Google Font name to load | None |

#### Light Mode Colors

| Attribute | Description | Default |
|-----------|-------------|---------|
| `primary-color` | Main accent color | `#3498db` |
| `background-color` | Form background | `#ffffff` |
| `text-color` | General text color | `#333333` |
| `border-color` | Border color | `#aaaaaa` |
| `button-color` | Button background | Same as primary-color |
| `button-text-color` | Button text color | `#ffffff` |
| `heading-color` | Heading text color | Same as text-color |
| `input-background-color` | Input field background | Same as background-color |
| `input-text-color` | Input text color | Same as text-color |
| `input-border-color` | Input border color | Same as border-color |
| `fieldset-background-color` | Fieldset background | Same as background-color |
| `success-color` | Success message color | `#4caf50` |
| `error-color` | Error message color | `#d32f2f` |
| `progress-color` | Progress bar color | Same as primary-color |

#### Dark Mode Colors

| Attribute | Description | Default |
|-----------|-------------|---------|
| `dark-primary-color` | Primary accent for dark mode | `#60a5fa` |
| `dark-background-color` | Background for dark mode | `#1e2026` |
| `dark-text-color` | Text color for dark mode | `#e9ecef` |
| `dark-border-color` | Border color for dark mode | `#495057` |
| `dark-button-color` | Button background for dark mode | Same as dark-primary-color |
| `dark-button-text-color` | Button text for dark mode | `#ffffff` |
| `dark-heading-color` | Heading text for dark mode | Same as dark-text-color |
| `dark-input-background-color` | Input background for dark mode | Same as dark-background-color |
| `dark-input-text-color` | Input text for dark mode | Same as dark-text-color |
| `dark-input-border-color` | Input border for dark mode | Same as dark-border-color |
| `dark-fieldset-background-color` | Fieldset background for dark mode | Same as dark-background-color |
| `dark-success-color` | Success color for dark mode | `#4ade80` |
| `dark-error-color` | Error color for dark mode | `#f87171` |
| `dark-progress-color` | Progress color for dark mode | Same as dark-primary-color |

### Example: Custom Theme

```html
<web-inquiry-form
  api-url="https://your-api.com/leads"
  form-title="Get In Touch"
  primary-color="#6366f1"
  background-color="#ffffff"
  button-color="#4f46e5"
  button-text-color="#ffffff"
  heading-color="#1e1b4b"
  input-background-color="#f8fafc"
  fieldset-background-color="#f1f5f9"
  success-color="#10b981"
  error-color="#ef4444"
  border-radius="12px"
  google-font="Inter"
  font-size="16px"
></web-inquiry-form>
```

### Form Data Structure

```javascript
{
  firstName: "...",
  lastName: "...",
  email: "...",
  phone: "...",
  phoneExt: "...",
  businessName: "...",
  businessPhone: "...",
  businessPhoneExt: "...",
  businessEmail: "...",
  businessServices: "...",
  billingAddress: {
    street: "...",
    aptUnit: "...",
    city: "...",
    state: "...",
    zipCode: "...",
    country: "..."
  },
  preferredContact: "phone|email|text|businessPhone|businessEmail",
  serviceDesired: "Web Development|App Development",
  hasWebsite: "yes|no",
  websiteAddress: "...",
  message: "...",
  isFormSubmission: true
}
```

### Screenshots

![Form Step 1](assets/form1.png)
![Form Step 2](assets/form2.png)
![Form Step 3](assets/form3.png)
![Form Step 4](assets/form4.png)
![Form Step 5](assets/form5.png)

#### Dark Mode

![Dark Mode](assets/form_dark.png)

#### Custom Themes

![Custom Theme 1 Light](assets/custom1-light.png)
![Custom Theme 1 Dark](assets/custom1-dark.png)
![Custom Theme 2 Light](assets/custom2-light.png)
![Custom Theme 2 Dark](assets/custom2-dark.png)
![Custom Theme 3 Light](assets/custom3-light.png)
![Custom Theme 3 Dark](assets/custom3-dark.png)

---

## Minimalist Contact Form

A simple, clean contact form for basic inquiries with name, email, and message fields.

![Minimalist Contact Form](assets/light.png)

### Basic Usage

```html
<contact-form
  endpoint="https://your-api-endpoint.com/api/contact"
></contact-form>
```

### Features

- Simple 3-field form (name, email, message)
- Clean, minimal design
- Instant validation
- Success/error toast notifications
- Smooth animations

### Customization Attributes

#### Basic Configuration

| Attribute | Description | Default |
|-----------|-------------|---------|
| `endpoint` | API endpoint URL | `https://example.com/api/contact` |
| `theme` | Force theme: "light", "dark", or auto | Auto-detect |

#### Styling

| Attribute | Description | Default |
|-----------|-------------|---------|
| `primary-color` | Main accent color and button background | `#3b82f6` |
| `background-color` | Form background color | `#ffffff` |
| `text-color` | Text color for labels and headings | `#374151` |
| `border-color` | General border color | `#d1d5db` |
| `border-radius` | Corner roundness | `6px` |
| `font-family` | Custom font family | System fonts |
| `font-size` | Base font size | `14px` |
| `google-font` | Google Font name to load | None |
| `heading` | Form heading text | None |
| `input-background-color` | Input field background | Same as background-color |
| `input-text-color` | Input field text color | Same as text-color |
| `input-border-color` | Input field border color | Same as border-color |
| `button-text-color` | Button text color | `#ffffff` |
| `success-message` | Custom success message | "Message sent successfully!" |
| `error-message` | Custom error message | "Failed to send message. Please try again." |

#### Dark Mode Styling

| Attribute | Description | Default |
|-----------|-------------|---------|
| `dark-primary-color` | Primary color for dark mode | `#60a5fa` |
| `dark-background-color` | Background for dark mode | `#1f2937` |
| `dark-text-color` | Text color for dark mode | `#f9fafb` |
| `dark-border-color` | General border color for dark mode | `#4b5563` |
| `dark-input-background-color` | Input background for dark mode | Same as dark-background-color |
| `dark-input-text-color` | Input text color for dark mode | Same as dark-text-color |
| `dark-input-border-color` | Input border color for dark mode | Same as dark-border-color |
| `dark-button-text-color` | Button text color for dark mode | `#ffffff` |

### Example: Custom Theme

```html
<contact-form
  endpoint="https://your-api.com/contact"
  primary-color="#8b5cf6"
  background-color="#ffffff"
  text-color="#1f2937"
  border-color="#d1d5db"
  input-background-color="#f9fafb"
  input-text-color="#111827"
  input-border-color="#9ca3af"
  button-text-color="#ffffff"
  border-radius="12px"
  google-font="Inter"
  font-size="14px"
  heading="Get In Touch"
  dark-primary-color="#a78bfa"
  dark-background-color="#1f2937"
  dark-text-color="#f9fafb"
  dark-input-background-color="#111827"
  dark-input-text-color="#e5e7eb"
  dark-input-border-color="#6b7280"
  dark-button-text-color="#1f2937"
></contact-form>
```

### Form Data Structure

```javascript
{
  name: "...",
  email: "...",
  message: "..."
}
```

### Screenshots

![Light Mode](assets/light.png)
![Dark Mode](assets/dark.png)

---

## Events

Both forms dispatch custom events you can listen for:

```javascript
// Form submitted (before API call)
document.addEventListener('form-submit', (event) => {
  console.log('Form data:', event.detail);
});

// Form successfully submitted
document.addEventListener('form-success', (event) => {
  console.log('Success:', event.detail.message);
});

// Form submission error
document.addEventListener('form-error', (event) => {
  console.error('Error:', event.detail.error);
});
```

## Server Requirements

Your API endpoint should:
- Accept POST requests with `Content-Type: application/json`
- Return 2xx status code for successful submissions
- Return 4xx/5xx status code for errors
- Optionally return JSON with a `message` property for error details

## Browser Compatibility

Works with all modern browsers that support:
- Custom Elements v1
- Shadow DOM v1
- ES6+ JavaScript

Compatible with: Chrome, Firefox, Safari, Edge

## Changelog

### v1.0.15 (Latest)
- Web inquiry form: Updated `:host` `max-width` from 632px to 600px (both forms now 600px visual width)

### v1.0.14
- Increased form widths for better readability on larger screens
- Contact form: Updated `max-width` from 500px to 600px
- Web inquiry form: Updated `:host` `max-width` from 532px to 632px 

### v1.0.13
- Added `input-text-color` and `dark-input-text-color` attributes to contact form for independent control of input field text colors
- Added `input-border-color` and `dark-input-border-color` attributes to contact form for independent control of input field border colors
- Fixed attribute inheritance issues where input fields were incorrectly inheriting from general text and border color attributes
- All contact form color attributes now work independently with proper fallback behavior

### v1.0.12
- Added letter-spacing to contact form for improved readability (1px on headings, 0.75px on content)

### v1.0.11
- Improved mobile responsive design for contact form with optimized font sizes, padding, and spacing on screens below 480px

### v1.0.10
- Updated README with complete documentation for contact form attributes including button text color customization

### v1.0.9
- Added `button-text-color` and `dark-button-text-color` attributes to contact form for customizable button text

### v1.0.8
- Restored 768px breakpoint for web-inquiry-form to prevent text overflow on tablets

### v1.0.7
- Removed 768px breakpoint (reverted in v1.0.8 due to text overflow)

### v1.0.6
- Fixed contact form name field spacing on mobile to be consistent with other form fields

### v1.0.5
- Fixed contact form total width to be 500px (including padding) using `box-sizing: border-box`
- Improved consistency between contact form and web inquiry form sizing

### v1.0.4
- Standardized form widths to 564px for better consistency
- Added responsive name field breakpoint at 480px for improved mobile experience

### v1.0.2
- Added assets folder to npm package for proper image display in documentation

### v1.0.1
- Initial release with web inquiry form and minimalist contact form
- Multi-step form with validation
- Dark mode support
- Full customization via attributes

## [License](LICENSE)

## Author

DevManSam - [GitHub](https://github.com/DevManSam777)

## Related Projects

- [DevLeads](https://github.com/DevManSam777/devleads) - Full lead management system
- [Portfolio Template](https://github.com/DevManSam777/portfolio_template) - Professional portfolio template using these forms
