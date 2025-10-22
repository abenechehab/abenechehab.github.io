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
        },
        {
            location: [43.3026, 5.3691],
            title: "Marseille, France",
            images: [
                {
                    url: "/assets/img/travel/marseille/1.jpg",
                    caption: "Notre Dame de la Garde church seen from St Charles central station."
                },
                {
                    url: "/assets/img/travel/marseille/2.jpg",
                    caption: "Cheering on the Moroccan football olympic team during the Paris 2024 Olympic games."
                },
                {
                    url: "/assets/img/travel/marseille/3.jpg",
                    caption: "The beautiful Martigues beach, a commune northwest of Marseille."
                },
            ]
        },
        {
            location: [42.6977, 23.3219],
            title: "Sofia, Bulgaria",
            images: [
                {
                    url: "/assets/img/travel/sofia/1.jpg",
                    caption: "Front of view of the Patriarchal Cathedral of St. Alexander Nevsky."
                },
                {
                    url: "/assets/img/travel/sofia/2.jpg",
                    caption: "Side view of the Patriarchal Cathedral of St. Alexander Nevsky during the evening."
                },
                {
                    url: "/assets/img/travel/sofia/3.jpg",
                    caption: "The National Palace of Culture in Sofia, Bulgaria."
                },
            ]
        },
        {
            location: [41.7170, 26.3511],
            title: "Night train: Istanbul-Sofia",
            images: [
                {
                    url: "/assets/img/travel/istanbul-sofia/1.jpg",
                    caption: "Crossing the Bulgarian-turkish border in Kapıkule railway station."
                },
                {
                    url: "/assets/img/travel/istanbul-sofia/2.jpg",
                    caption: "The Istanbul (Halkali) Sofia express train."
                },
            ]
        },
        {
            location: [43.9037, 25.9699],
            title: "Night Bus: Bucharest-Istanbul",
            images: [
                {
                    url: "/assets/img/travel/bucharest-istanbul/1.png",
                    caption: "The Romanian-Bulgarian border at the Ruse-Giurgiu crossing."
                },
            ]
        },
        {
            location: [41.0082, 28.9784],
            title: "Istanbul, Turkey",
            images: [
                {
                    url: "/assets/img/travel/istanbul/1.jpg",
                    caption: "The Hagia Sophia Grand Mosque."
                },
            ]
        },
        {
            location: [40.1885, 29.0610],
            title: "Bursa, Turkey",
            images: [
                {
                    url: "/assets/img/travel/bursa/1.jpg",
                    caption: "Osman Gazi Türbesi, the final resting place of the first Ottoman sultan."
                },
            ]
        },
        {
            location: [37.9355, 27.3461],
            title: "Ephesus Archaeological Site",
            images: [
                {
                    url: "/assets/img/travel/epheseus/1.jpg",
                    caption: "Ephesus was a city in Ancient Greece."
                },
                {
                    url: "/assets/img/travel/epheseus/2.jpg",
                    caption: "Epheseus' Roman theatre is capable of holding 24,000 spectators."
                },
                {
                    url: "/assets/img/travel/epheseus/3.jpg",
                    caption: "An overview of the Epheseus cite, including the Library of Celsus."
                },
            ]
        },
        {
            location: [44.4268, 26.1025],
            title: "Bucharest, Romania",
            images: [
                {
                    url: "/assets/img/travel/bucharest/1.jpg",
                    caption: "The Palace of the Parliament also known as the People's House after the Revolution against Nicolae Ceaușescu."
                },
                {
                    url: "/assets/img/travel/bucharest/2.jpg",
                    caption: "Transylvanian pink marble, extensively used inside the Palace of the Parliament."
                },
                {
                    url: "/assets/img/travel/bucharest/3.jpg",
                    caption: "One of the 480 chandeliers feature in the Palace of the Parliament."
                },
            ]
        },
        {
            location: [41.5147, 19.7884],
            title: "Krujë, Albania",
            images: [
                {
                    url: "/assets/img/travel/kruje/1.jpg",
                    caption: "The Krujë Castle, the center of Skanderbeg's rebellion against the Ottoman Empire."
                },
                {
                    url: "/assets/img/travel/kruje/2.jpg",
                    caption: "Old Bazaar of Krujë."
                },
                {
                    url: "/assets/img/travel/kruje/3.jpg",
                    caption: "Krujë Castle ruins and an overview of the surrounding hills."
                },
            ]
        },
        {
            location: [41.3275, 19.8187],
            title: "Tirana, Albania",
            images: [
                {
                    url: "/assets/img/travel/tirana/1.jpg",
                    caption: "The Lana river crossing Tirana."
                },
                {
                    url: "/assets/img/travel/tirana/2.jpg",
                    caption: "The National History Museum of Albania, featuring 'The Albanians' mural mosaic."
                },
                {
                    url: "/assets/img/travel/tirana/3.jpg",
                    caption: "Ramadan vibes in the city center of Tirana."
                },
            ]
        },
        {
            location: [38.4237, 27.1428],
            title: "Izmir, Turkey",
            images: [
                {
                    url: "/assets/img/travel/izmir/1.jpg",
                    caption: "Foça harbor at night, a municipality and district of İzmir Province."
                },
            ]
        },
        {
            location: [48.5734, 7.7521],
            title: "Strasbourg, France",
            images: [
                {
                    url: "/assets/img/travel/strasbourg/1.jpg",
                    caption: "The 'Petite France' or Französel (in alsacien) during the night."
                },
                {
                    url: "/assets/img/travel/strasbourg/2.jpg",
                    caption: "The Rhine river crossing Strasbourg."
                },
            ]
        },
        {
            location: [48.1351, 11.5820],
            title: "Munich, Germany",
            images: [
                {
                    url: "/assets/img/travel/munich/1.jpg",
                    caption: "."
                },
            ]
        },
        {
            location: [37.3891, -5.9845],
            title: "Sevilla, Spain",
            images: [
                {
                    url: "/assets/img/travel/sevilla/1.jpg",
                    caption: "."
                },
                                {
                    url: "/assets/img/travel/sevilla/2.jpg",
                    caption: "."
                },
                                {
                    url: "/assets/img/travel/sevilla/3.jpg",
                    caption: "."
                },
            ]
        },
        {
            location: [43.9289, 2.1464],
            title: "Albi, France",
            images: [
                {
                    url: "/assets/img/travel/albi/1.jpg",
                    caption: "albi - 2 photo"
                },
                {
                    url: "/assets/img/travel/albi/2.jpg",
                    caption: "albi - 2 photo"
                }
            ]
        },
        {
            location: [52.37278, 4.89361],
            title: "Amsterdam, Netherlands",
            images: [
                {
                    url: "/assets/img/travel/amsterdam/1.jpg",
                    caption: "amsterdam - 1 photo"
                }
            ]
        },
        {
            // Note: you need to find correct coords
            location: [43.5804, 7.1251],
            title: "Antibes, France",
            images: [
                {
                    url: "/assets/img/travel/antibes/1.jpg",
                    caption: "antibes - 1 photo"
                }
            ]
        },
        {
            location: [48.1478, 17.1072],
            title: "Bratislava, Slovakia",
            images: [
                {
                    url: "/assets/img/travel/bratislava/1.jpg",
                    caption: "bratislava - 2 photo"
                },
                {
                    url: "/assets/img/travel/bratislava/2.jpg",
                    caption: "bratislava - 2 photo"
                }
            ]
        },
        {
            location: [50.8477, 4.3572],
            title: "Brussels, Belgium",
            images: [
                {
                    url: "/assets/img/travel/brussels/1.jpg",
                    caption: "brussels - 1 photo"
                }
            ]
        },
        {
            location: [47.4979, 19.0402],
            title: "Budapest, Hungary",
            images: [
                {
                    url: "/assets/img/travel/budapest/1.jpg",
                    caption: "budapest - 2 photo"
                },
                {
                    url: "/assets/img/travel/budapest/2.jpg",
                    caption: "budapest - 2 photo"
                }
            ]
        },
        {
            location: [48.9567, 4.3631],
            title: "Châlons-en-Champagne, France",
            images: [
                {
                    url: "/assets/img/travel/chalons en champagne/1.jpg",
                    caption: "chalons en champagne - 3 photo"
                },
                {
                    url: "/assets/img/travel/chalons en champagne/2.jpg",
                    caption: "chalons en champagne - 3 photo"
                },
                {
                    url: "/assets/img/travel/chalons en champagne/3.jpg",
                    caption: "chalons en champagne - 3 photo"
                }
            ]
        },
        {
            location: [55.6761, 12.5683],
            title: "Copenhagen, Denmark",
            images: [
                {
                    url: "/assets/img/travel/copenhagen/1.jpg",
                    caption: "copenhagen - 5 photo"
                },
                {
                    url: "/assets/img/travel/copenhagen/2.jpg",
                    caption: "copenhagen - 5 photo"
                },
                {
                    url: "/assets/img/travel/copenhagen/3.jpg",
                    caption: "copenhagen - 5 photo"
                },
                {
                    url: "/assets/img/travel/copenhagen/4.jpg",
                    caption: "copenhagen - 5 photo"
                },
                {
                    url: "/assets/img/travel/copenhagen/5.jpg",
                    caption: "copenhagen - 5 photo"
                }
            ]
        },
        {
            location: [37.8893, 4.7793],
            title: "Córdoba, Spain",
            images: [
                {
                    url: "/assets/img/travel/cordoba/1.jpg",
                    caption: "cordoba - 1 photo"
                }
            ]
        },
        {
            location: [43.7700, 11.2577],
            title: "Florence, Italy",
            images: [
                {
                    url: "/assets/img/travel/firenze/1.jpg",
                    caption: "firenze - 1 photo"
                }
            ]
        },
        {
            location: [37.1825, 3.6012],
            title: "Granada, Spain",
            images: [
                {
                    url: "/assets/img/travel/granada/1.jpg",
                    caption: "granada - 3 photo"
                },
                {
                    url: "/assets/img/travel/granada/2.jpg",
                    caption: "granada - 3 photo"
                },
                {
                    url: "/assets/img/travel/granada/3.jpg",
                    caption: "granada - 3 photo"
                }
            ]
        },
        {
            location: [6.1944, 106.8229],
            title: "Jakarta, Indonesia",
            images: [
                {
                    url: "/assets/img/travel/jakarta/1.jpg",
                    caption: "jakarta - 4 photo"
                },
                {
                    url: "/assets/img/travel/jakarta/2.jpg",
                    caption: "jakarta - 4 photo"
                },
                {
                    url: "/assets/img/travel/jakarta/3.jpg",
                    caption: "jakarta - 4 photo"
                },
                {
                    url: "/assets/img/travel/jakarta/4.jpg",
                    caption: "jakarta - 4 photo"
                }
            ]
        },
        {
            location: [3.1319, 101.6841],
            title: "Kuala Lumpur, Malaysia",
            images: [
                {
                    url: "/assets/img/travel/kualalumpur/1.jpg",
                    caption: "kualalumpur - 5 photo"
                },
                {
                    url: "/assets/img/travel/kualalumpur/2.jpg",
                    caption: "kualalumpur - 5 photo"
                },
                {
                    url: "/assets/img/travel/kualalumpur/3.jpg",
                    caption: "kualalumpur - 5 photo"
                },
                {
                    url: "/assets/img/travel/kualalumpur/4.jpg",
                    caption: "kualalumpur - 5 photo"
                },
                {
                    url: "/assets/img/travel/kualalumpur/5.jpg",
                    caption: "kualalumpur - 5 photo"
                }
            ]
        },
        {
            location: [49.4953, 0.1011],
            title: "Le Havre, France",
            images: [
                {
                    url: "/assets/img/travel/lehavre/1.jpg",
                    caption: "lehavre - 3 photo"
                },
                {
                    url: "/assets/img/travel/lehavre/2.jpg",
                    caption: "lehavre - 3 photo"
                },
                {
                    url: "/assets/img/travel/lehavre/3.jpg",
                    caption: "lehavre - 3 photo"
                }
            ]
        },
        {
            location: [38.7223, 9.1393],
            title: "Lisbon, Portugal",
            images: [
                {
                    url: "/assets/img/travel/lisbon/1.jpg",
                    caption: "lisbon - 3 photo"
                },
                {
                    url: "/assets/img/travel/lisbon/2.jpg",
                    caption: "lisbon - 3 photo"
                },
                {
                    url: "/assets/img/travel/lisbon/3.jpg",
                    caption: "lisbon - 3 photo"
                }
            ]
        },
        {
            location: [49.8153, 6.1296],
            title: "Luxembourg City, Luxembourg",
            images: [
                {
                    url: "/assets/img/travel/luxembourg/1.jpg",
                    caption: "luxembourg - 2 photo"
                },
                {
                    url: "/assets/img/travel/luxembourg/2.jpg",
                    caption: "luxembourg - 2 photo"
                }
            ]
        },
        {
            location: [45.7640, 4.8357],
            title: "Lyon, France",
            images: [
                {
                    url: "/assets/img/travel/lyon/1.jpg",
                    caption: "lyon - 2 photo"
                },
                {
                    url: "/assets/img/travel/lyon/2.jpg",
                    caption: "lyon - 2 photo"
                }
            ]
        },
        {
            location: [40.4167, 3.7033],
            title: "Madrid, Spain",
            images: [
                {
                    url: "/assets/img/travel/madrid/1.jpg",
                    caption: "madrid - 4 photo"
                },
                {
                    url: "/assets/img/travel/madrid/2.jpg",
                    caption: "madrid - 4 photo"
                },
                {
                    url: "/assets/img/travel/madrid/3.jpg",
                    caption: "madrid - 4 photo"
                },
                {
                    url: "/assets/img/travel/madrid/4.jpg",
                    caption: "madrid - 4 photo"
                }
            ]
        },
        {
            location: [21.4241, 39.8173],
            title: "Makkah, Saudi Arabia",
            images: [
                {
                    url: "/assets/img/travel/makkah/1.jpg",
                    caption: "makkah - 2 photo"
                },
                {
                    url: "/assets/img/travel/makkah/2.jpg",
                    caption: "makkah - 2 photo"
                }
            ]
        },
        {
            location: [59.9122, 10.7313],
            title: "Oslo, Norway",
            images: [
                {
                    url: "/assets/img/travel/oslo/1.jpg",
                    caption: "oslo - 3 photo"
                },
                {
                    url: "/assets/img/travel/oslo/2.jpg",
                    caption: "oslo - 3 photo"
                },
                {
                    url: "/assets/img/travel/oslo/3.jpg",
                    caption: "oslo - 3 photo"
                }
            ]
        },
        {
            location: [39.5727, 2.6569],
            title: "Palma de Mallorca, Spain",
            images: [
                {
                    url: "/assets/img/travel/palma/1.jpg",
                    caption: "palma - 1 photo"
                }
            ]
        },
        {
            location: [41.1579, 8.6291],
            title: "Porto, Portugal",
            images: [
                {
                    url: "/assets/img/travel/porto/1.jpg",
                    caption: "porto - 1 photo"
                }
            ]
        },
        {
            location: [50.0755, 14.4378],
            title: "Prague, Czech Republic",
            images: [
                {
                    url: "/assets/img/travel/prague/1.jpg",
                    caption: "prague - 4 photo"
                },
                {
                    url: "/assets/img/travel/prague/2.jpg",
                    caption: "prague - 4 photo"
                },
                {
                    url: "/assets/img/travel/prague/3.jpg",
                    caption: "prague - 4 photo"
                },
                {
                    url: "/assets/img/travel/prague/4.jpg",
                    caption: "prague - 4 photo"
                }
            ]
        },
        {
            location: [49.2583, 4.0317],
            title: "Reims",
            images: [
                {
                    url: "/assets/img/travel/reims/1.jpg",
                    caption: "reims - 1 photo"
                }
            ]
        },
        {
            location: [41.8967, 12.4822],
            title: "Rome, Italy",
            images: [
                {
                    url: "/assets/img/travel/roma/1.jpg",
                    caption: "roma - 4 photo"
                },
                {
                    url: "/assets/img/travel/roma/2.jpg",
                    caption: "roma - 4 photo"
                },
                {
                    url: "/assets/img/travel/roma/3.jpg",
                    caption: "roma - 4 photo"
                },
                {
                    url: "/assets/img/travel/roma/4.jpg",
                    caption: "roma - 4 photo"
                }
            ]
        },
        {
            location: [1.3521, 103.8198],
            title: "Singapore",
            images: [
                {
                    url: "/assets/img/travel/singapore/1.jpg",
                    caption: "singapore - 3 photo"
                },
                {
                    url: "/assets/img/travel/singapore/2.jpg",
                    caption: "singapore - 3 photo"
                },
                {
                    url: "/assets/img/travel/singapore/3.jpg",
                    caption: "singapore - 3 photo"
                }
            ]
        },
        {
            location: [6.3690, 34.8888],
            title: "Tanzania",
            images: [
                {
                    url: "/assets/img/travel/tanzania/1.jpg",
                    caption: "tanzania - 2 photo"
                },
                {
                    url: "/assets/img/travel/tanzania/2.jpg",
                    caption: "tanzania - 2 photo"
                }
            ]
        },
        {
            location: [41.9029, 12.4534],
            title: "Vatican City",
            images: [
                {
                    url: "/assets/img/travel/vatican/1.jpg",
                    caption: "vatican - 2 photo"
                },
                {
                    url: "/assets/img/travel/vatican/2.jpg",
                    caption: "vatican - 2 photo"
                }
            ]
        },
        {
            location: [44.9676, 5.5301],
            title: "Vercors massif",
            images: [
                {
                    url: "/assets/img/travel/vercors/1.jpg",
                    caption: "vercors - 4 photo"
                },
                {
                    url: "/assets/img/travel/vercors/2.jpg",
                    caption: "vercors - 4 photo"
                },
                {
                    url: "/assets/img/travel/vercors/3.jpg",
                    caption: "vercors - 4 photo"
                },
                {
                    url: "/assets/img/travel/vercors/4.jpg",
                    caption: "vercors - 4 photo"
                }
            ]
        },
        {
            location: [6.1333328, 39.3166654],
            title: "Zanzibar, Tanzania",
            images: [
                {
                    url: "/assets/img/travel/zanzibar/1.jpg",
                    caption: "zanzibar - 1 photo"
                }
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