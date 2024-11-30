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
    
    L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors &copy; <a href="https://carto.com/attributions">CARTO</a>',
        maxZoom: 19
    }).addTo(map);
    
    // Your travel data
    // const travelData = [
    //     {
    //         location: [51.5074, -0.1278],
    //         title: "London, UK",
    //         images: [
    //             {
    //                 url: "/assets/img/travel/london1.jpg",
    //                 caption: "Big Ben at sunset"
    //             },
    //             {
    //                 url: "/assets/img/travel/london2.jpg",
    //                 caption: "Tower Bridge"
    //             }
    //         ]
    //     },
    //     // Add more locations here
    // ];

    const travelData = [
        {
            location: [41.1171, 16.8719],
            title: "Bari, Italy",
            images: [
                {
                    url: "/assets/img/travel/bari/1.jpg",
                    caption: "Bari beach at sunset"
                },
                {
                    url: "/assets/img/travel/bari/2.jpg",
                    caption: "Bari old town streets"
                },
                {
                    url: "/assets/img/travel/bari/3.jpg",
                    caption: "Local wedding at Bari Cathedral"
                }
            ]  // Add your image paths and captions here
        },
        {
            location: [41.3233, 19.4411],
            title: "Durrës, Albania",
            images: [
                {
                    url: "/assets/img/travel/durres/1.jpg",
                    caption: "Roman amphitheatre"
                },
                {
                    url: "/assets/img/travel/durres/2.jpg",
                    caption: "View of Durres Beaches at night from the hotel"
                },
                {
                    url: "/assets/img/travel/durres/3.jpg",
                    caption: "Durres sea front"
                }
            ]
        },
        {
            location: [41.2202, 18.1565],
            title: "Adriatic Sea Ferry: Bari-Durres",
            images: [
                {
                    url: "/assets/img/travel/bari-durres/1.jpg",
                    caption: "Bari harbor at night"
                },
                {
                    url: "/assets/img/travel/bari-durres/2.jpg",
                    caption: "In the middle of the adreatic sea"
                },
                {
                    url: "/assets/img/travel/bari-durres/3.jpg",
                    caption: "Durres port from the ferry"
                }
            ]
        },
        {
            location: [48.4036, 2.4681],
            title: "Milly-la-Forêt, France",
            images: [
                {
                    url: "/assets/img/travel/milly_la_foret/1.jpg",
                    caption: "A rainy bike trip!"
                },
                {
                    url: "/assets/img/travel/milly_la_foret/2.jpg",
                    caption: "A slug savouring chocolate in milly-la-forêt !"
                }
            ]
        },
        {
            location: [43.0799, -79.0747],
            title: "Niagara Falls",
            images: [
                {
                    url: "/assets/img/travel/niagara/1.jpg",
                    caption: "The magnificent Niagara falls!"
                },
                {
                    url: "/assets/img/travel/niagara/2.jpg",
                    caption: "In the niagara falls cruise."
                },
                {
                    url: "/assets/img/travel/niagara/3.jpg",
                    caption: "Niagara falls seen from the boat."
                }
            ]
        },
        {
            location: [43.6532, -79.3832],
            title: "Toronto, Canada",
            images: [
                {
                    url: "/assets/img/travel/toronto/1.jpg",
                    caption: "Toronto from the taxi boat!"
                },
                {
                    url: "/assets/img/travel/toronto/2.jpg",
                    caption: "Toronto city hall at night."
                },
                {
                    url: "/assets/img/travel/toronto/3.jpg",
                    caption: "A massive school bus in the streets of Toronto!"
                },
                {
                    url: "/assets/img/travel/toronto/4.jpg",
                    caption: "Canadian pastries and tarts at the St Lawrence Market"
                }
            ]
        },
        {
            location: [48.7784, 9.1800],
            title: "Stuttgart, Germany",
            images: [   
                {
                    url: "/assets/img/travel/stuttgart/1.jpg",
                    caption: "The Hans-im-Glück-Brunnen or 'Lucky Hans Fountain' in Stuttgart."
                },
                {
                    url: "/assets/img/travel/stuttgart/2.jpg",
                    caption: "A quit sunday in one of Stuttgart's parks."
                },
            ]
        },
        {
            location: [48.2082, 16.3738],
            title: "Vienna, Austria",
            images: [
                {
                    url: "/assets/img/travel/vienna/1.jpg",
                    caption: "The Ankeruhr (Anker clock) in Vienna, Austria."
                },
                {
                    url: "/assets/img/travel/vienna/2.jpg",
                    caption: "Presenting our blogpost poster at ICLR 2024 conference at Messe Wien."
                },
                {
                    url: "/assets/img/travel/vienna/3.jpg",
                    caption: "The entrance of Messe Wien during ICLR 2024 conference."
                },
            ]
        },
        {
            location: [31.6182, -7.9679],
            title: "UM6P University, Benguerir, Morocco",
            images: [
                {
                    url: "/assets/img/travel/um6p/1.JPG",
                    caption: "Mentoring at the ThinkAI Hackathon at UM6P university in Benguerir, Morocco."
                },
                {
                    url: "/assets/img/travel/um6p/2.JPG",
                    caption: "During an intervention at Dr. Soufiane Hayou's talk."
                },
                {
                    url: "/assets/img/travel/um6p/3.JPG",
                    caption: "Attending the final pitches of the ThinkAI Hackathon candidates!"
                },
                {
                    url: "/assets/img/travel/um6p/4.JPG",
                    caption: "During an intervention at Dr. Amine Mohamed Aboussalah's talk."
                },
            ]
        }
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