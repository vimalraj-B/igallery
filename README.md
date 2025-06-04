
# Ex.08 Design of Interactive Image Gallery
## Date:04.06.2025

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Interactive Photo Gallery</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(to right, #f7f8f8, #acbb78);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 30px 10px;
        }

        h1 {
            margin-bottom: 30px;
            font-size: 2.5rem;
            color: #333;
            animation: fadeSlideDown 1s ease-in-out;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            width: 100%;
            max-width: 1200px;
            animation: fadeIn 1.5s ease-in;
        }

        .gallery img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.4s ease, box-shadow 0.4s ease;
        }

        .gallery img:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        .lightbox {
            display: none;
            position: fixed;
            inset: 0;
            background-color: rgba(0, 0, 0, 0.85);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .lightbox.active {
            display: flex;
        }

        .lightbox img {
            max-width: 90vw;
            max-height: 90vh;
            border-radius: 12px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
            animation: zoomIn 0.5s ease forwards;
        }

        .close {
            position: absolute;
            top: 30px;
            right: 40px;
            font-size: 40px;
            color: #fff;
            text-decoration: none;
            transition: color 0.3s ease;
            z-index: 1001;
        }

        .close:hover {
            color: #ccc;
        }

        @keyframes fadeSlideDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes zoomIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        footer {
            margin-top: 40px;
            text-align: center;
            color: #444;
            font-size: 0.9rem;
        }

        @media (max-width: 1024px) {
            .gallery {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        @media (max-width: 768px) {
            .gallery {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 480px) {
            .gallery {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <h1>Interactive Photo Gallery</h1>
    <div class="gallery">
        <img src="images/thumbnail1.png" alt="Image 1">
        <img src="images/thumbnail2.png" alt="Image 2">
        <img src="images/thumbnail3.png" alt="Image 3">
        <img src="images/thumbnail4.png" alt="Image 4">
        <img src="images/thumbnail5.png" alt="Image 5">
        <img src="images/thumbnail6.png" alt="Image 6">
        <img src="images/thumbnail7.png" alt="Image 7">
        <img src="images/thumbnail8.png" alt="Image 8">
        <img src="images/thumbnail1.png" alt="Image 9">
        <img src="images/thumbnail2.png" alt="Image 10">
        <img src="images/thumbnail3.png" alt="Image 11">
        <img src="images/thumbnail4.png" alt="Image 12">
    </div>

    <div class="lightbox" id="lightbox">
        <span class="close">&times;</span>
        <img src="" alt="Preview">
    </div>

    <footer>
        &copy; 2025 Interactive Photo Gallery. All rights reserved.
    </footer>

    <script>
        const galleryImages = document.querySelectorAll('.gallery img');
        const lightbox = document.getElementById('lightbox');
        const lightboxImage = lightbox.querySelector('img');
        const closeBtn = lightbox.querySelector('.close');

        galleryImages.forEach(img => {
            img.addEventListener('click', () => {
                lightboxImage.src = img.src;
                lightbox.classList.add('active');
            });
        });

        closeBtn.addEventListener('click', () => {
            lightbox.classList.remove('active');
        });

        lightbox.addEventListener('click', (e) => {
            if (e.target === lightbox || e.target === closeBtn) {
                lightbox.classList.remove('active');
            }
        });
    </script>
</body>
</html>
```
## OUTPUT:
![443558991-dc88af6e-41be-4599-b47e-ed148c0c53fd](https://github.com/user-attachments/assets/16c8acea-961e-4e58-b2bf-99d913d554dc)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
