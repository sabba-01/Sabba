# Sabba
/ecommerce-handmade
├── public/
├── src/
│   ├── App.jsx
│   ├── index.js
│   ├── components/
│   │   ├── ProductCard.jsx
│   │   └── Navbar.jsx
│   └── data/products.js
├── tailwind.config.js
└── package.json
// src/data/products.js
const products = [
  {
    id: 1,
    name: "Handmade Scented Candle",
    description: "Aromatherapy candle made with natural wax.",
    price: 250,
    image: "https://via.placeholder.com/200x200?text=Candle"
  },
  {
    id: 2,
    name: "Woolen Craft Doll",
    description: "Cute handmade woolen doll for decor or gifting.",
    price: 400,
    image: "https://via.placeholder.com/200x200?text=Doll"
  },
  {
    id: 3,
    name: "Hand-Painted Mug",
    description: "Unique mug with hand-painted floral design.",
    price: 320,
    image: "https://via.placeholder.com/200x200?text=Mug"
  }
];

// src/components/ProductCard.jsx
import React from "react";

const ProductCard = ({ product }) => {
  return (
    <div className="bg-white rounded-2xl shadow-md p-4">
      <img src={product.image} alt={product.name} className="rounded-xl mb-4" />
      <h2 className="text-xl font-semibold">{product.name}</h2>
      <p className="text-sm text-gray-500">{product.description}</p>
      <p className="text-lg font-bold mt-2">₹{product.price}</p>
      <button className="mt-3 bg-pink-500 text-white py-2 px-4 rounded-xl hover:bg-pink-600">
        Buy Now
      </button>
    </div>
  );
};

export default ProductCard;// src/components/Navbar.jsx
import React from "react";

const Navbar = () => {
  return (
    <nav className="bg-white shadow-md p-4 flex justify-between items-center">
      <h1 className="text-2xl font-bold text-pink-600">Handmade Bazaar</h1>
      <div>
        <button className="bg-pink-500 text-white px-4 py-2 rounded-xl">Cart</button>
      </div>
    </nav>
  );
};

export default Navbar;
// src/App.jsx
import React from "react";
import products from "./data/products";
import ProductCard from "./components/ProductCard";
import Navbar from "./components/Navbar";

const App = () => {
  return (
    <div className="bg-gray-100 min-h-screen">
      <Navbar />
      <div className="p-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        {products.map(product => (
          <ProductCard key={product.id} product={product} />
        ))}
      </div>
    </div>
  );
};

export default App;
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -pcontent: ["./src/**/*.{js,jsx}"],
