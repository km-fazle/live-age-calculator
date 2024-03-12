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
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>Live Age</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" />
    <script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Poppins">
    <style>
        .bold-poppins {
            font-family: 'Poppins', sans-serif;
            font-weight: bold;
        }

        body {
            background-color: #11172D;
        }

        #age-container {
            background-color: #1D293B;
        }

        #age-display {
            color: #FFFFFF;
        }

        p {
            color: #9CA3AF;
        }
    </style>
<script nonce="c209c9af-d1a4-48ae-95fa-73fa12cbcec3">try{(function(w,d){!function(du,dv,dw,dx){du[dw]=du[dw]||{};du[dw].executed=[];du.zaraz={deferred:[],listeners:[]};du.zaraz.q=[];du.zaraz._f=function(dy){return async function(){var dz=Array.prototype.slice.call(arguments);du.zaraz.q.push({m:dy,a:dz})}};for(const dA of["track","set","debug"])du.zaraz[dA]=du.zaraz._f(dA);du.zaraz.init=()=>{var dB=dv.getElementsByTagName(dx)[0],dC=dv.createElement(dx),dD=dv.getElementsByTagName("title")[0];dD&&(du[dw].t=dv.getElementsByTagName("title")[0].text);du[dw].x=Math.random();du[dw].w=du.screen.width;du[dw].h=du.screen.height;du[dw].j=du.innerHeight;du[dw].e=du.innerWidth;du[dw].l=du.location.href;du[dw].r=dv.referrer;du[dw].k=du.screen.colorDepth;du[dw].n=dv.characterSet;du[dw].o=(new Date).getTimezoneOffset();if(du.dataLayer)for(const dH of Object.entries(Object.entries(dataLayer).reduce(((dI,dJ)=>({...dI[1],...dJ[1]})),{})))zaraz.set(dH[0],dH[1],{scope:"page"});du[dw].q=[];for(;du.zaraz.q.length;){const dK=du.zaraz.q.shift();du[dw].q.push(dK)}dC.defer=!0;for(const dL of[localStorage,sessionStorage])Object.keys(dL||{}).filter((dN=>dN.startsWith("_zaraz_"))).forEach((dM=>{try{du[dw]["z_"+dM.slice(7)]=JSON.parse(dL.getItem(dM))}catch{du[dw]["z_"+dM.slice(7)]=dL.getItem(dM)}}));dC.referrerPolicy="origin";dC.src="/cdn-cgi/zaraz/s.js?z="+btoa(encodeURIComponent(JSON.stringify(du[dw])));dB.parentNode.insertBefore(dC,dB)};["complete","interactive"].includes(dv.readyState)?zaraz.init():du.addEventListener("DOMContentLoaded",zaraz.init)}(w,d,"zarazData","script");})(window,document)}catch(e){throw fetch("/cdn-cgi/zaraz/t"),e;};</script></head>

<body class="font-sans">

    <!-- Your Live Age Calculator Section -->
    <section class="py-20">
        <div class="container mx-auto animate__animated animate__fadeIn">
            <h3
                class="flex justify-center text-3xl leading-normal font-semibold text-gray-900 mb-8 animate__animated animate__fadeInDown bold-poppins">
                <img src="/1.png" alt="KM" width="100" height="100">
            </h3>

            <div id="age-container"
                class="bg-white shadow-lg rounded-lg overflow-hidden p-6 mx-auto w-full md:w-3/4 lg:w-2/3 animate__animated animate__fadeInUp">
                <div class="text-center">
                    <div id="age-display" class="text-4xl font-bold mb-4 text-white"></div>
                    <p class="text-gray-400">Time is going fast. Do what you want to do in life</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Background Audio -->


    <!-- Your Live Age Calculator Script -->
    <script>
        // Assuming the date of birth is 1st January 2000
        const birthDate = new Date('1999-03-12T00:00:00');

        function calculateAge() {
            const birthDate = new Date(2002, 2, 12, 2.5); // 2 for March since months are 0-indexed
            const now = new Date();

            let years = now.getFullYear() - birthDate.getFullYear();
            let months = now.getMonth() - birthDate.getMonth();
            let days = now.getDate() - birthDate.getDate();
            let hours = now.getHours() - birthDate.getHours();
            let minutes = now.getMinutes() - birthDate.getMinutes();
            let seconds = now.getSeconds() - birthDate.getSeconds();

            // Adjust calculations if necessary (e.g., if now's day is less than birthDate's day, borrow a month)
            if (seconds < 0) { seconds +=60; minutes--; } 
            if (minutes < 0) { minutes +=60; hours--; } 
            if (hours < 0) { hours +=24; days--; } 
            if (days < 0) { // Use 30.44 days per month, the average month length in days days +=Math.round(30.44);
                months--; 
            } 
            if (months < 0) { months +=12; years--; } 
            const ageDisplay = document.getElementById('age-display');
            ageDisplay.innerHTML = `You Are <span style="font-family: 'Poppins', sans-serif; font-weight: bold; color: #D1D5DB;">${years}</span>
            Years ${months} Months ${days} Days ${hours} Hours ${minutes} Minutes ${seconds} Seconds Old`;
        }

        // Call the function once to display the age immediately
        calculateAge();

        // Update the age every second
        setInterval(calculateAge, 1000);

        // New script to play and loop audio
        document.addEventListener('DOMContentLoaded', (event) => {
            const audioElement = document.getElementById('background-audio');
            audioElement.play();
        });
    </script>

</body>

</html>
