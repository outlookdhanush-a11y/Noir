<!DOCTYPE html>
<html lang="en" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>N O I R — Luxury Perfume Maison</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Cormorant Garamond & Montserrat for clean luxury typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Montserrat:wght@200;300;400;500;600&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        'noir-bg': '#070707',
                        'noir-card': '#0E0E0E',
                        'noir-border': '#1F1F1F',
                        'noir-gold': '#C5A059',
                        'noir-gold-muted': '#8E733E',
                        'noir-subtext': '#777777',
                    },
                    fontFamily: {
                        serif: ['"Cormorant Garamond"', 'Georgia', 'serif'],
                        sans: ['"Montserrat"', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #070707;
            color: #E5E5E5;
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
        }

        .font-garamond {
            font-family: 'Cormorant Garamond', Georgia, serif;
        }

        /* Subtle borders matching reference */
        .card-border {
            border: 1px solid rgba(255, 255, 255, 0.08);
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .card-border:hover {
            border-color: rgba(197, 160, 89, 0.4);
            transform: translateY(-2px);
        }

        /* Glass Drawer */
        .glass-panel {
            background: rgba(12, 12, 12, 0.92);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-left: 1px solid rgba(255, 255, 255, 0.08);
        }

        ::-webkit-scrollbar {
            width: 4px;
        }
        ::-webkit-scrollbar-track {
            background: #070707;
        }
        ::-webkit-scrollbar-thumb {
            background: #222;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #C5A059;
        }

        .img-zoom {
            transition: transform 0.7s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .group:hover .img-zoom {
            transform: scale(1.04);
        }
    </style>
</head>
<body class="selection:bg-noir-gold selection:text-black">

    <!-- Toast Banner -->
    <div id="toast" class="fixed top-20 right-5 z-50 transform translate-x-full transition-transform duration-300 ease-in-out">
        <div class="bg-noir-card border-l-2 border-noir-gold px-5 py-3 shadow-2xl flex items-center space-x-3 text-xs tracking-widest uppercase text-white">
            <i class="fa-solid fa-check text-noir-gold"></i>
            <span id="toast-message">Added to Bag</span>
        </div>
    </div>

    <!-- Announcement Bar -->
    <div class="bg-black text-center py-2 px-4 text-[10px] tracking-[0.3em] uppercase text-noir-subtext border-b border-noir-border/50">
        Complimentary Express Worldwide Shipping & Master Discovery Sample With Every Order
    </div>

    <!-- MAIN NAVIGATION HEADER -->
    <header class="sticky top-0 z-40 bg-noir-bg/95 backdrop-blur-md border-b border-noir-border/60">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <button onclick="toggleMobileNav()" class="md:hidden text-white hover:text-noir-gold transition">
                <i class="fa-solid fa-bars text-lg"></i>
            </button>

            <!-- Brand Logo -->
            <a href="#" class="font-garamond text-2xl md:text-3xl tracking-[0.4em] font-normal text-white hover:text-noir-gold transition-colors duration-300">
                N O I R
            </a>

            <!-- Desktop Links -->
            <nav class="hidden md:flex items-center space-x-12 text-[11px] tracking-[0.25em] font-light uppercase text-noir-subtext">
                <a href="#collection" class="hover:text-white transition">Collection</a>
                <a href="#extraits" class="hover:text-white transition">Extraits</a>
                <a href="#artistry" class="hover:text-white transition">The Craft</a>
            </nav>

            <!-- Right Actions -->
            <div class="flex items-center space-x-6">
                <button onclick="openEnquireModal()" class="text-[11px] tracking-[0.25em] uppercase text-noir-gold hover:text-white transition hidden sm:block">
                    ENQUIRE
                </button>

                <button id="cart-btn" class="relative text-white hover:text-noir-gold transition py-2" aria-label="Bag">
                    <i class="fa-solid fa-bag-shopping text-base"></i>
                    <span id="cart-count" class="absolute -top-1 -right-2 bg-noir-gold text-black font-semibold text-[9px] w-4 h-4 rounded-full flex items-center justify-center">0</span>
                </button>
            </div>
        </div>

        <!-- Mobile Menu Drawer -->
        <div id="mobile-nav" class="hidden md:hidden bg-noir-card border-b border-noir-border px-6 py-6 space-y-4 text-xs tracking-[0.2em] uppercase text-noir-subtext">
            <a href="#collection" onclick="toggleMobileNav()" class="block hover:text-white">Collection</a>
            <a href="#extraits" onclick="toggleMobileNav()" class="block hover:text-white">Extraits</a>
            <a href="#artistry" onclick="toggleMobileNav()" class="block hover:text-white">The Craft</a>
            <button onclick="openEnquireModal(); toggleMobileNav();" class="block text-noir-gold pt-2">Enquire Concierge</button>
        </div>
    </header>

    <!-- HERO SECTION -->
    <section class="relative min-h-[75vh] flex items-center justify-center overflow-hidden border-b border-noir-border/50">
        <div class="absolute inset-0 bg-cover bg-center filter brightness-[0.35] contrast-125"
             style="background-image: url('https://images.unsplash.com/photo-1615397349754-cfa2066a298e?q=80&w=1920&auto=format&fit=crop');">
        </div>
        <div class="absolute inset-0 bg-gradient-to-t from-noir-bg via-noir-bg/50 to-transparent"></div>

        <div class="relative z-10 max-w-4xl mx-auto px-6 text-center space-y-6 py-20">
            <span class="text-noir-gold text-[10px] tracking-[0.4em] uppercase font-light">EXTRAIT DE PARFUM ARCHIVE</span>
            
            <h1 class="font-garamond text-4xl sm:text-6xl md:text-7xl font-light tracking-wide text-white leading-tight">
                DARK NOCTURNAL <br/>
                <span class="italic font-garamond text-noir-gold">NOIR</span> FORMULATIONS
            </h1>

            <p class="max-w-xl mx-auto text-noir-subtext text-xs sm:text-sm font-light tracking-wider leading-relaxed">
                Hand-poured in Grasse. Aged for 90 days in dark oak casks to achieve 35% concentration depth.
            </p>

            <div class="pt-4 flex justify-center gap-4">
                <a href="#collection" class="border border-noir-gold text-noir-gold hover:bg-noir-gold hover:text-black px-8 py-3.5 text-[10px] tracking-[0.3em] uppercase transition duration-300">
                    Explore Vault
                </a>
            </div>
        </div>
    </section>

    <!-- FILTER & SEARCH BAR -->
    <section class="py-10 border-b border-noir-border/40 bg-noir-bg">
        <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center gap-6">
            
            <!-- Category Tabs -->
            <div class="flex flex-wrap gap-3 justify-center md:justify-start" id="filter-buttons">
                <button onclick="filterCategory('all')" class="filter-btn text-[10px] uppercase tracking-[0.2em] px-4 py-2 border border-noir-gold text-noir-gold">All Works</button>
                <button onclick="filterCategory('Extrait')" class="filter-btn text-[10px] uppercase tracking-[0.2em] px-4 py-2 border border-noir-border text-noir-subtext hover:border-white hover:text-white transition">Extraits</button>
                <button onclick="filterCategory('Eau de Parfum')" class="filter-btn text-[10px] uppercase tracking-[0.2em] px-4 py-2 border border-noir-border text-noir-subtext hover:border-white hover:text-white transition">Eau de Parfum</button>
                <button onclick="filterCategory('Amber & Oud')" class="filter-btn text-[10px] uppercase tracking-[0.2em] px-4 py-2 border border-noir-border text-noir-subtext hover:border-white hover:text-white transition">Amber & Oud</button>
            </div>

            <!-- Search Field -->
            <div class="relative w-full md:w-64">
                <input type="text" id="search-input" onkeyup="renderCatalog()" placeholder="Search scent or note..." 
                       class="w-full bg-noir-card border border-noir-border focus:border-noir-gold text-[11px] text-white px-4 py-2.5 tracking-wider focus:outline-none transition">
                <i class="fa-solid fa-magnifying-glass absolute right-3.5 top-3 text-noir-subtext text-xs"></i>
            </div>
        </div>
    </section>

    <!-- PERFUME CATALOG GRID (Matches 2-Column Mobile Layout from Screenshot) -->
    <section id="collection" class="py-16 bg-noir-bg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6">
            
            <!-- Grid matching 2-column mobile reference -->
            <div id="catalog-grid" class="grid grid-cols-2 lg:grid-cols-4 gap-3 sm:gap-6">
                <!-- Dynamic Injection -->
            </div>
        </div>
    </section>

    <!-- ARTISTRY & CRAFT SECTION -->
    <section id="artistry" class="py-24 border-t border-noir-border bg-noir-card">
        <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div class="space-y-6">
                <span class="text-noir-gold text-[10px] tracking-[0.3em] uppercase">NOCTURNAL EXTRAITS</span>
                <h2 class="font-garamond text-3xl sm:text-5xl text-white font-light leading-tight">
                    DARK VELVET & <br/>
                    <span class="italic text-noir-gold">FACETED AMBER GLASS</span>
                </h2>
                <p class="text-noir-subtext text-xs sm:text-sm leading-relaxed font-light tracking-wide">
                    Each NOIR vessel is constructed from weighted obsidian and amber glass designed to protect volatile raw extract oils against light degradation. 
                </p>
                <div class="grid grid-cols-2 gap-6 pt-4 border-t border-noir-border">
                    <div>
                        <span class="font-garamond text-2xl text-white block">35%</span>
                        <span class="text-[10px] uppercase tracking-widest text-noir-subtext">Pure Essential Extract</span>
                    </div>
                    <div>
                        <span class="font-garamond text-2xl text-white block">16+ HRS</span>
                        <span class="text-[10px] uppercase tracking-widest text-noir-subtext">Continuous Sillage</span>
                    </div>
                </div>
            </div>

            <div class="relative aspect-4/5 overflow-hidden border border-noir-border">
                <img src="https://images.unsplash.com/photo-1592945403244-b3fbafd7f539?q=80&w=1000&auto=format&fit=crop" 
                     alt="NOIR Artisanal Craft" class="w-full h-full object-cover">
                <div class="absolute inset-0 bg-gradient-to-t from-black via-transparent to-transparent"></div>
            </div>
        </div>
    </section>

    <!-- SHOPPING BAG DRAWER -->
    <div id="cart-drawer" class="fixed inset-0 z-50 overflow-hidden pointer-events-none transition-opacity duration-300 opacity-0">
        <div id="cart-backdrop" class="absolute inset-0 bg-black/80 backdrop-blur-sm" onclick="toggleCart()"></div>

        <div class="fixed inset-y-0 right-0 max-w-full flex pl-10">
            <div id="cart-panel" class="w-screen max-w-md glass-panel text-white pointer-events-auto transform translate-x-full transition-transform duration-300 ease-in-out flex flex-col">
                <div class="p-6 border-b border-noir-border flex items-center justify-between">
                    <span class="font-garamond text-xl tracking-widest uppercase">YOUR SELECTIONS</span>
                    <button onclick="toggleCart()" class="text-noir-subtext hover:text-white p-2">
                        <i class="fa-solid fa-xmark text-lg"></i>
                    </button>
                </div>

                <div id="cart-items" class="flex-1 overflow-y-auto p-6 space-y-6">
                    <!-- Dynamic Cart Rows -->
                </div>

                <div class="p-6 border-t border-noir-border bg-black space-y-4">
                    <div class="flex justify-between items-center text-xs tracking-widest">
                        <span class="text-noir-subtext uppercase">Subtotal</span>
                        <span id="cart-subtotal" class="font-garamond text-lg text-noir-gold">$0.00</span>
                    </div>
                    <button onclick="alert('Proceeding to private checkout...')" class="w-full bg-noir-gold hover:bg-white text-black py-3.5 text-[10px] tracking-[0.3em] uppercase font-medium transition">
                        Checkout
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- PRODUCT QUICK DETAIL MODAL -->
    <div id="detail-modal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/90 backdrop-blur-md hidden">
        <div class="bg-noir-card border border-noir-border max-w-3xl w-full rounded-none overflow-hidden relative max-h-[90vh] overflow-y-auto">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-noir-subtext hover:text-white z-10 p-2">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>

            <div id="modal-content" class="grid grid-cols-1 md:grid-cols-2">
                <!-- Injected content -->
            </div>
        </div>
    </div>

    <!-- CONCIERGE ENQUIRE MODAL -->
    <div id="enquire-modal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/90 backdrop-blur-md hidden">
        <div class="bg-noir-card border border-noir-border max-w-md w-full p-8 relative">
            <button onclick="closeEnquireModal()" class="absolute top-4 right-4 text-noir-subtext hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <span class="text-noir-gold text-[10px] tracking-[0.3em] uppercase">PRIVATE CONCIERGE</span>
            <h3 class="font-garamond text-2xl text-white mt-1 mb-6">FRAGRANCE ENQUIRY</h3>
            <form onsubmit="event.preventDefault(); alert('Enquiry received. A NOIR specialist will contact you shortly.'); closeEnquireModal();" class="space-y-4">
                <input type="text" placeholder="Full Name" required class="w-full bg-noir-bg border border-noir-border text-xs text-white p-3 focus:border-noir-gold focus:outline-none">
                <input type="email" placeholder="Email Address" required class="w-full bg-noir-bg border border-noir-border text-xs text-white p-3 focus:border-noir-gold focus:outline-none">
                <textarea placeholder="Specify fragrance interest or custom formulation query..." rows="3" class="w-full bg-noir-bg border border-noir-border text-xs text-white p-3 focus:border-noir-gold focus:outline-none"></textarea>
                <button type="submit" class="w-full border border-noir-gold text-noir-gold hover:bg-noir-gold hover:text-black py-3 text-[10px] tracking-[0.3em] uppercase transition">Send Enquiry</button>
            </form>
        </div>
    </div>

    <!-- FOOTER -->
    <footer class="bg-black border-t border-noir-border py-16">
        <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center gap-8">
            <div class="text-center md:text-left space-y-2">
                <span class="font-garamond text-2xl tracking-[0.4em] text-white">N O I R</span>
                <p class="text-[10px] tracking-[0.2em] text-noir-subtext uppercase">PARIS • GRASSE • NEW YORK</p>
            </div>
            <div class="flex space-x-8 text-[10px] tracking-[0.2em] uppercase text-noir-subtext">
                <a href="#collection" class="hover:text-white">Vault</a>
                <a href="#artistry" class="hover:text-white">Artistry</a>
                <button onclick="openEnquireModal()" class="hover:text-noir-gold">Enquire</button>
            </div>
            <div class="text-[10px] tracking-[0.2em] text-noir-subtext">
                © 2026 NOIR PARFUMS. ALL RIGHTS RESERVED.
            </div>
        </div>
    </footer>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // High-Resolution Fragrance Catalog matching screenshot reference photography
        const products = [
            {
                id: 1,
                name: "Amber Oud",
                type: "EXTRAIT",
                size: "100ML",
                altSizes: ["50ML", "100ML"],
                price100: 340,
                price50: 220,
                category: "Extrait",
                scentGroup: "Amber & Oud",
                // Photorealistic Amber Oud faceted golden cap photography on silk drapery
                image: "https://images.unsplash.com/photo-1547887537-6158d64c35b3?q=80&w=800&auto=format&fit=crop",
                topNotes: "Crushed Saffron, Smoked Bergamot",
                heartNotes: "Oman Incense, Amber Resin",
                baseNotes: "Wild Cambodian Oud, Vanilla Bean"
            },
            {
                id: 2,
                name: "Amber Oud",
                type: "EXTRAIT",
                size: "50ML",
                altSizes: ["50ML", "100ML"],
                price100: 340,
                price50: 220,
                category: "Extrait",
                scentGroup: "Amber & Oud",
                // Amber crystal faceted golden cap with warm candle lighting & saffron background
                image: "https://images.unsplash.com/photo-1594035910387-fea47794261f?q=80&w=800&auto=format&fit=crop",
                topNotes: "Saffron Threads, Nutmeg",
                heartNotes: "Dark Iris, Smoked Amber",
                baseNotes: "Aged Oud Wood, Roasted Tonka"
            },
            {
                id: 3,
                name: "Myth",
                type: "EAU DE PARFUM",
                size: "100ML",
                altSizes: ["50ML", "100ML"],
                price100: 280,
                price50: 180,
                category: "Eau de Parfum",
                scentGroup: "Dark Floral",
                // Matte black bottle on dark surface with rose petals
                image: "https://images.unsplash.com/photo-1523293182086-7651a899d37f?q=80&w=800&auto=format&fit=crop",
                topNotes: "Midnight Plum, Pink Pepper",
                heartNotes: "Nocturnal Black Rose, Velvet Iris",
                baseNotes: "Smokey Birch Tar, Musk"
            },
            {
                id: 4,
                name: "Myth",
                type: "EAU DE PARFUM",
                size: "50ML",
                altSizes: ["50ML", "100ML"],
                price100: 280,
                price50: 180,
                category: "Eau de Parfum",
                scentGroup: "Dark Floral",
                // Angle shot of sleek matte black bottle on dark textured leather
                image: "https://images.unsplash.com/photo-1588405748880-12d1d2a59f75?q=80&w=800&auto=format&fit=crop",
                topNotes: "Midnight Rose, Currant",
                heartNotes: "Smoked Tobacco, Clove",
                baseNotes: "Black Leather, Patchouli"
            },
            {
                id: 5,
                name: "Obsidian",
                type: "EXTRAIT",
                size: "100ML",
                altSizes: ["50ML", "100ML"],
                price100: 360,
                price50: 240,
                category: "Extrait",
                scentGroup: "Leather & Wood",
                image: "https://images.unsplash.com/photo-1615397349754-cfa2066a298e?q=80&w=800&auto=format&fit=crop",
                topNotes: "Cardamom, Smoked Incense",
                heartNotes: "Tuscan Leather, Cypress",
                baseNotes: "Ebony Wood, Amber Crystals"
            },
            {
                id: 6,
                name: "Velvet Rose",
                type: "EXTRAIT",
                size: "50ML",
                altSizes: ["50ML", "100ML"],
                price100: 310,
                price50: 200,
                category: "Extrait",
                scentGroup: "Dark Floral",
                image: "https://images.unsplash.com/photo-1592945403244-b3fbafd7f539?q=80&w=800&auto=format&fit=crop",
                topNotes: "Bulgarian Rose, Bergamot",
                heartNotes: "Cacao Pod, Damask Rose",
                baseNotes: "Labdanum, Bourbon Vanilla"
            }
        ];

        let activeCategory = 'all';
        let cart = [];

        document.addEventListener('DOMContentLoaded', () => {
            renderCatalog();
        });

        function filterCategory(cat) {
            activeCategory = cat;
            const btns = document.querySelectorAll('.filter-btn');
            btns.forEach(b => {
                b.classList.remove('border-noir-gold', 'text-noir-gold');
                b.classList.add('border-noir-border', 'text-noir-subtext');
            });
            event.target.classList.remove('border-noir-border', 'text-noir-subtext');
            event.target.classList.add('border-noir-gold', 'text-noir-gold');

            renderCatalog();
        }

        function renderCatalog() {
            const grid = document.getElementById('catalog-grid');
            const search = document.getElementById('search-input').value.toLowerCase();

            grid.innerHTML = '';

            const filtered = products.filter(p => {
                const matchCat = (activeCategory === 'all') || 
                                 (p.category === activeCategory) || 
                                 (p.scentGroup.includes(activeCategory));
                const matchSearch = p.name.toLowerCase().includes(search) || 
                                    p.type.toLowerCase().includes(search);
                return matchCat && matchSearch;
            });

            filtered.forEach(p => {
                const currentPrice = p.size === '100ML' ? p.price100 : p.price50;

                const card = document.createElement('div');
                // Clean card styling matching screenshot 2-column format
                card.className = "card-border bg-noir-card flex flex-col justify-between group cursor-pointer";
                card.onclick = () => openModal(p.id);

                card.innerHTML = `
                    <div class="relative aspect-[4/5] overflow-hidden bg-black">
                        <img src="${p.image}" alt="${p.name}" class="w-full h-full object-cover img-zoom">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-40 group-hover:opacity-10 transition"></div>
                    </div>

                    <div class="p-4 sm:p-5 flex flex-col justify-between flex-1">
                        <div>
                            <!-- Serif Title as shown in reference -->
                            <h3 class="font-garamond text-lg sm:text-2xl text-white font-normal tracking-wide group-hover:text-noir-gold transition">
                                ${p.name}
                            </h3>
                            <!-- Subtitle meta as shown in reference -->
                            <p class="text-[9px] sm:text-[10px] tracking-[0.25em] text-noir-subtext uppercase mt-1">
                                ${p.type} &nbsp;·&nbsp; ${p.size}
                            </p>
                        </div>

                        <div class="pt-4 flex items-center justify-between border-t border-noir-border/50 mt-4">
                            <span class="font-garamond text-sm sm:text-base text-noir-gold">$${currentPrice}</span>
                            <button onclick="event.stopPropagation(); addToCart(${p.id})" class="text-[9px] tracking-[0.2em] uppercase text-white hover:text-noir-gold transition">
                                + Add Bag
                            </button>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Cart Drawer Operations
        function addToCart(id) {
            const item = products.find(p => p.id === id);
            const price = item.size === '100ML' ? item.price100 : item.price50;

            const existing = cart.find(c => c.id === id);
            if (existing) {
                existing.qty += 1;
            } else {
                cart.push({ ...item, price: price, qty: 1 });
            }

            updateCartUI();
            showToast(`Added ${item.name} (${item.size}) to Bag`);
        }

        function updateCartUI() {
            const container = document.getElementById('cart-items');
            const totalCount = cart.reduce((sum, i) => sum + i.qty, 0);
            const subtotal = cart.reduce((sum, i) => sum + (i.price * i.qty), 0);

            document.getElementById('cart-count').innerText = totalCount;
            document.getElementById('cart-subtotal').innerText = `$${subtotal.toFixed(2)}`;

            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-20 text-noir-subtext space-y-3">
                        <i class="fa-solid fa-bag-shopping text-3xl opacity-30"></i>
                        <p class="font-garamond text-lg text-white">YOUR BAG IS EMPTY</p>
                    </div>
                `;
                return;
            }

            container.innerHTML = '';
            cart.forEach((c, index) => {
                const row = document.createElement('div');
                row.className = "flex items-center gap-4 pb-4 border-b border-noir-border";
                row.innerHTML = `
                    <img src="${c.image}" class="w-14 h-16 object-cover border border-noir-border">
                    <div class="flex-1">
                        <h4 class="font-garamond text-base text-white">${c.name}</h4>
                        <p class="text-[9px] text-noir-subtext tracking-widest uppercase">${c.type} · ${c.size}</p>
                        <p class="text-xs text-noir-gold mt-1">$${c.price}</p>
                    </div>
                    <div class="flex items-center gap-2">
                        <button onclick="changeQty(${index}, -1)" class="text-noir-subtext hover:text-white text-xs px-1">-</button>
                        <span class="text-xs text-white">${c.qty}</span>
                        <button onclick="changeQty(${index}, 1)" class="text-noir-subtext hover:text-white text-xs px-1">+</button>
                    </div>
                `;
                container.appendChild(row);
            });
        }

        function changeQty(index, delta) {
            cart[index].qty += delta;
            if (cart[index].qty <= 0) cart.splice(index, 1);
            updateCartUI();
        }

        function toggleCart() {
            const drawer = document.getElementById('cart-drawer');
            const panel = document.getElementById('cart-panel');
            if (drawer.classList.contains('opacity-0')) {
                updateCartUI();
                drawer.classList.remove('opacity-0', 'pointer-events-none');
                panel.classList.remove('translate-x-full');
            } else {
                panel.classList.add('translate-x-full');
                setTimeout(() => drawer.classList.add('opacity-0', 'pointer-events-none'), 300);
            }
        }

        document.getElementById('cart-btn').addEventListener('click', toggleCart);

        // Quick Detail Modal
        function openModal(id) {
            const p = products.find(item => item.id === id);
            const content = document.getElementById('modal-content');

            content.innerHTML = `
                <div class="aspect-4/5 bg-black">
                    <img src="${p.image}" alt="${p.name}" class="w-full h-full object-cover">
                </div>
                <div class="p-8 space-y-6 flex flex-col justify-between bg-noir-card">
                    <div class="space-y-4">
                        <span class="text-noir-gold text-[9px] tracking-[0.3em] uppercase">${p.type}</span>
                        <h2 class="font-garamond text-3xl sm:text-4xl text-white font-normal">${p.name}</h2>
                        <p class="text-xs text-noir-subtext tracking-widest uppercase">${p.size} &nbsp;·&nbsp; 35% CONCENTRATION</p>
                        
                        <div class="space-y-2 pt-4 border-t border-noir-border text-xs">
                            <p class="text-white"><strong class="text-noir-gold font-normal">Top Notes:</strong> ${p.topNotes}</p>
                            <p class="text-white"><strong class="text-noir-gold font-normal">Heart Notes:</strong> ${p.heartNotes}</p>
                            <p class="text-white"><strong class="text-noir-gold font-normal">Base Notes:</strong> ${p.baseNotes}</p>
                        </div>
                    </div>

                    <div class="pt-6 border-t border-noir-border flex items-center justify-between gap-4">
                        <span class="font-garamond text-2xl text-white">$${p.size === '100ML' ? p.price100 : p.price50}</span>
                        <button onclick="addToCart(${p.id}); closeModal();" class="border border-noir-gold bg-noir-gold text-black hover:bg-white py-3 px-6 text-[10px] tracking-[0.3em] uppercase font-medium transition">
                            Add to Bag
                        </button>
                    </div>
                </div>
            `;

            document.getElementById('detail-modal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('detail-modal').classList.add('hidden');
        }

        function openEnquireModal() {
            document.getElementById('enquire-modal').classList.remove('hidden');
        }
        function closeEnquireModal() {
            document.getElementById('enquire-modal').classList.add('hidden');
        }
        function toggleMobileNav() {
            document.getElementById('mobile-nav').classList.toggle('hidden');
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-message').innerText = msg;
            toast.classList.remove('translate-x-full');
            setTimeout(() => toast.classList.add('translate-x-full'), 3000);
        }
    </script>
</body>
</html>
