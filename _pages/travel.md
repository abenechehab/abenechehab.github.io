---
# _pages/travel.md
layout: page
title: Travel
permalink: /travel/
description: Places I've visited around the world
nav: false
nav_order: 6
---

<div class="travel-container">
    <div id="travel-map"></div>
    <div id="image-showcase" class="image-showcase">
        <div class="swiper">
            <div class="swiper-wrapper">
                <!-- Slides will be dynamically added here -->
            </div>
            <div class="swiper-pagination"></div>
            <div class="swiper-button-next"></div>
            <div class="swiper-button-prev"></div>
        </div>
    </div>
</div>

<!-- Load external libraries -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.css" />
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/8.4.7/swiper-bundle.min.css" />

<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/8.4.7/swiper-bundle.min.js"></script>

<style>
    .travel-container {
        margin-top: 2rem;
    }
    
    #travel-map {
        height: 500px;
        width: 100%;
        border-radius: 8px;
        margin-bottom: 20px;
    }
    
    .image-showcase {
        display: none;
        margin-top: 20px;
        background: var(--global-bg-color);
        padding: 20px;
        border-radius: 8px;
        border: 1px solid var(--global-divider-color);
    }
    
    .swiper {
        width: 100%;
        height: 400px;
    }
    
    .swiper-slide {
        text-align: center;
    }
    
    .swiper-slide img {
        max-height: 300px;
        max-width: 100%;
        object-fit: contain;
    }
    
    .caption {
        margin-top: 10px;
        padding: 10px;
        background: var(--global-bg-color);
        border-radius: 4px;
        color: var(--global-text-color);
    }
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    // Initialize the map
    const map = L.map('travel-map').setView([20, 0], 2);
    
    // Option 1: JAWG Maps Streets (free, no API key required)
    L.tileLayer('https://tile.jawg.io/jawg-streets/{z}/{x}/{y}.png?access-token=anonymous', {
        attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank">&copy; <b>Jawg</b>Maps</a> &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
        minZoom: 0,
        maxZoom: 22
    }).addTo(map);
    
    // Option 2 (alternative if JAWG doesn't work):
    // L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}.png', {
    //     attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors &copy; <a href="https://carto.com/attributions">CARTO</a>',
    //     maxZoom: 19
    // }).addTo(map);
    
    // Your travel data
    const travelData = [
        {
            location: [51.5074, -0.1278],
            title: "London, UK",
            images: [
                {
                    url: "/assets/img/travel/london1.jpg",
                    caption: "Big Ben at sunset"
                },
                {
                    url: "/assets/img/travel/london2.jpg",
                    caption: "Tower Bridge"
                }
            ]
        },
        // Add more locations here
    ];
    
    let swiper = null;
    
    // Add markers to the map
    travelData.forEach(place => {
        const marker = L.marker(place.location)
            .addTo(map)
            .bindPopup(place.title);
            
        marker.on('click', () => showImages(place));
    });
    
    function showImages(place) {
        const showcase = document.getElementById('image-showcase');
        const swiperWrapper = document.querySelector('.swiper-wrapper');
        
        swiperWrapper.innerHTML = '';
        
        place.images.forEach(image => {
            const slide = document.createElement('div');
            slide.className = 'swiper-slide';
            slide.innerHTML = `
                <img src="${image.url}" alt="${image.caption}">
                <div class="caption">${image.caption}</div>
            `;
            swiperWrapper.appendChild(slide);
        });
        
        if (swiper) {
            swiper.destroy();
        }
        
        swiper = new Swiper('.swiper', {
            pagination: {
                el: '.swiper-pagination',
                clickable: true
            },
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev'
            }
        });
        
        showcase.style.display = 'block';
    }
});
</script>