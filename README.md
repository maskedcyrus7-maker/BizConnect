# BizConnect
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biz Connect | Trader Marketplace</title>
    <style>
        :root {
            --primary: #1e40af;
            --primary-hover: #1d4ed8;
            --bg: #f3f4f6;
            --card-bg: #ffffff;
            --text: #1f2937;
            --muted: #6b7280;
            --border: #e5e7eb;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
        }

        header {
            background-color: var(--primary);
            color: white;
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        header h1 {
            font-size: 1.5rem;
            letter-spacing: -0.5px;
        }

        .container {
            max-width: 1100px;
            margin: 2rem auto;
            padding: 0 1rem;
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 2rem;
        }

        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
        }

        .card {
            background: var(--card-bg);
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            border: 1px solid var(--border);
        }

        h2 {
            font-size: 1.25rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .form-group {
            margin-bottom: 1rem;
        }

        label {
            display: block;
            font-size: 0.875rem;
            font-weight: 600;
            margin-bottom: 0.25rem;
        }

        input, select, textarea {
            width: 100%;
            padding: 0.6rem;
            border: 1px solid var(--border);
            border-radius: 6px;
            font-size: 0.95rem;
        }

        button {
            width: 100%;
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 0.75rem;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.2s;
        }

        button:hover {
            background-color: var(--primary-hover);
        }

        .search-bar {
            margin-bottom: 1.5rem;
        }

        .listings-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 1rem;
        }

        .product-card {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: 1.25rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
        }

        .badge {
            display: inline-block;
            background: #dbeafe;
            color: var(--primary);
            font-size: 0.75rem;
            font-weight: 700;
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            margin-bottom: 0.5rem;
            width: fit-content;
        }

        .product-title {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 0.25rem;
        }

        .product-price {
            font-size: 1.15rem;
            font-weight: 700;
            color: #059669;
            margin-bottom: 0.5rem;
        }

        .product-desc {
            font-size: 0.9rem;
            color: var(--muted);
            margin-bottom: 1rem;
        }

        .trader-info {
            border-top: 1px solid var(--border);
            padding-top: 0.75rem;
            font-size: 0.85rem;
        }

        .contact-btn {
            display: block;
            text-align: center;
            background-color: #10b981;
            color: white;
            text-decoration: none;
            padding: 0.5rem;
            border-radius: 5px;
            font-weight: 600;
            margin-top: 0.5rem;
        }

        .contact-btn:hover {
            background-color: #059669;
        }
    </style>
</head>
<body>

    <header>
        <h1>Biz Connect</h1>
        <span>Trader Advertising Portal</span>
    </header>

    <div class="container">
        <!-- Form for Traders to Advertise Goods -->
        <section class="card">
            <h2>Post an Advert</h2>
            <form id="advertForm">
                <div class="form-group">
                    <label for="businessName">Trader / Business Name</label>
                    <input type="text" id="businessName" placeholder="e.g., Kampala Fresh Produce" required>
                </div>

                <div class="form-group">
                    <label for="productName">Product / Good Name</label>
                    <input type="text" id="productName" placeholder="e.g., 50kg Bag of Maize Flour" required>
                </div>

                <div class="form-group">
                    <label for="category">Category</label>
                    <select id="category">
                        <option value="Agriculture & Food">Agriculture & Food</option>
                        <option value="Electronics">Electronics</option>
                        <option value="Clothing & Textiles">Clothing & Textiles</option>
                        <option value="Hardware & Construction">Hardware & Construction</option>
                        <option value="Wholesale & General">Wholesale & General</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="price">Price (UGX)</label>
                    <input type="text" id="price" placeholder="e.g., 120,000" required>
                </div>

                <div class="form-group">
                    <label for="phone">Contact Phone / WhatsApp</label>
                    <input type="tel" id="phone" placeholder="e.g., +256 700 000000" required>
                </div>

                <div class="form-group">
                    <label for="description">Product Details & Location</label>
                    <textarea id="description" rows="3" placeholder="Describe quality, quantity, and pickup location..." required></textarea>
                </div>

                <button type="submit">Publish Advert</button>
            </form>
        </section>

        <!-- Marketplace Display -->
        <section>
            <div class="search-bar">
                <input type="text" id="searchInput" placeholder="Search for goods, categories, or traders...">
            </div>
            <div class="listings-grid" id="listingsContainer">
                <!-- Adverts will appear here -->
            </div>
        </section>
    </div>

    <script>
        // Sample initial listings so the app isn't empty on first load
        const defaultAdverts = [
            {
                business: "Mukono Agro Traders",
                product: "Organic Robusta Coffee Beans (100kg)",
                category: "Agriculture & Food",
                price: "850,000",
                phone: "+256700123456",
                description: "Sun-dried, sorted grade A beans ready for bulk buyers. Located near Mukono central market."
            },
            {
                business: "City Tech Supplies",
                product: "Solar Power Banks (20,000mAh)",
                category: "Electronics",
                price: "65,000",
                phone: "+256770987654",
                description: "Wholesale and retail available. Dual USB output with built-in LED torch."
            }
        ];

        // Load saved adverts from browser storage or use defaults
        let adverts = JSON.parse(localStorage.getItem('bizConnectAdverts')) || defaultAdverts;

        const form = document.getElementById('advertForm');
        const listingsContainer = document.getElementById('listingsContainer');
        const searchInput = document.getElementById('searchInput');

        function renderAdverts(filterText = '') {
            listingsContainer.innerHTML = '';
            
            const filtered = adverts.filter(ad => 
                ad.product.toLowerCase().includes(filterText.toLowerCase()) ||
                ad.business.toLowerCase().includes(filterText.toLowerCase()) ||
                ad.category.toLowerCase().includes(filterText.toLowerCase())
            );

            if (filtered.length === 0) {
                listingsContainer.innerHTML = '<p>No goods found matching your search.</p>';
                return;
            }

            filtered.forEach(ad => {
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <div>
                        <span class="badge">${ad.category}</span>
                        <div class="product-title">${ad.product}</div>
                        <div class="product-price">UGX ${ad.price}</div>
                        <p class="product-desc">${ad.description}</p>
                    </div>
                    <div class="trader-info">
                        <strong>Seller:</strong> ${ad.business}<br>
                        <strong>Tel:</strong> ${ad.phone}
                        <a href="tel:${ad.phone}" class="contact-btn">Call Trader</a>
                    </div>
                `;
                listingsContainer.appendChild(card);
            });
        }

        form.addEventListener('submit', (e) => {
            e.preventDefault();

            const newAdvert = {
                business: document.getElementById('businessName').value,
                product: document.getElementById('productName').value,
                category: document.getElementById('category').value,
                price: document.getElementById('price').value,
                phone: document.getElementById('phone').value,
                description: document.getElementById('description').value
            };

            adverts.unshift(newAdvert); // Add to top of list
            localStorage.setItem('bizConnectAdverts', JSON.stringify(adverts)); // Save locally
            
            renderAdverts();
            form.reset();
        });

        searchInput.addEventListener('input', (e) => {
            renderAdverts(e.target.value);
        });

        // Initial render
        renderAdverts();
    </script>
</body>
</html>
