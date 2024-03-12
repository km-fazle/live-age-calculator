# Live Age Calculator

The Live Age Calculator is a visually appealing web application that dynamically calculates and displays your age down to the second. Built with HTML, CSS, and JavaScript, it utilizes TailwindCSS for styling, Flatpickr for date handling, and Animate.css for smooth animations. This project aims to remind users of the fleeting nature of time and encourages them to make the most out of life.

## Features

- **Dynamic Age Calculation:** Calculates your age in years, months, days, hours, minutes, and seconds in real-time.
- **Sleek Design:** Utilizes TailwindCSS for a modern and responsive design.
- **Smooth Animations:** Enhances user experience with subtle animations via Animate.css.
- **Customizable:** Easily adjustable calculation logic to accommodate different date formats or age calculations.

## How It Works

Upon loading, the calculator immediately computes and displays the age based on a predefined date of birth. The age updates every second, offering a live countdown effect that illustrates the passage of time vividly.

### Date of Birth

The current calculation is based on a hardcoded date of birth. Users can modify the `birthDate` variable within the script tag to use a different date of birth.

1. Technologies Used
2. HTML5
3. CSS3 + TailwindCSS 2.2.19
4. JavaScript
5. Flatpickr for date handling
6. Animate.css for animations
7. Cloudflare
```html
<script>
    const birthDate = new Date('YYYY-MM-DDT00:00:00'); // Adjust to desired date of birth
</script>
