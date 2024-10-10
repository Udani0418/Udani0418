import React, { useState } from 'react';
import './App.css';

function App() {
  const [order, setOrder] = useState({
    customers: '',
    tableNumber: '',
    beverages: '',
    mainDish: '',
    sides: '',
    appetizers: '',
    desserts: '',
    soup: ''
  });

  const handleChange = (e) => {
    const { name, value } = e.target;
    setOrder((prevOrder) => ({
      ...prevOrder,
      [name]: value,
    }));
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log('Order submitted:', order);
    // Submit the order to the backend here
  };

  return (
    <div className="app">
      <div className="header">
        <h1>HOTEL NAME</h1>
        <div className="menu-bar">
          <button className="menu-btn">Menu</button>
          <button className="menu-btn">Log Out</button>
          <button className="menu-btn">Notification</button>
        </div>
      </div>
      <form className="order-form" onSubmit={handleSubmit}>
        <button className="take-order-btn">Take Order</button>

        <div className="form-group">
          <label>No of Customers</label>
          <select name="customers" value={order.customers} onChange={handleChange}>
            <option value="">Select</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
          </select>
        </div>

        <div className="form-group">
          <label>Table No</label>
          <select name="tableNumber" value={order.tableNumber} onChange={handleChange}>
            <option value="">Select Table</option>
            <option value="1">Table 1</option>
            <option value="2">Table 2</option>
            <option value="3">Table 3</option>
          </select>
        </div>

        <div className="form-group">
          <label>Beverages</label>
          <select name="beverages" value={order.beverages} onChange={handleChange}>
            <option value="">Select Beverage</option>
            <option value="water">Water</option>
            <option value="juice">Juice</option>
            <option value="soda">Soda</option>
          </select>
        </div>

        <div className="form-group">
          <label>Main Dish</label>
          <select name="mainDish" value={order.mainDish} onChange={handleChange}>
            <option value="">Select Main Dish</option>
            <option value="pizza">Pizza</option>
            <option value="pasta">Pasta</option>
            <option value="steak">Steak</option>
          </select>
        </div>

        <div className="form-group">
          <label>Sides</label>
          <select name="sides" value={order.sides} onChange={handleChange}>
            <option value="">Select Side</option>
            <option value="fries">Fries</option>
            <option value="salad">Salad</option>
          </select>
        </div>

        <div className="form-group">
          <label>Appetizers</label>
          <select name="appetizers" value={order.appetizers} onChange={handleChange}>
            <option value="">Select Appetizer</option>
            <option value="wings">Wings</option>
            <option value="nachos">Nachos</option>
          </select>
        </div>

        <div className="form-group">
          <label>Desserts</label>
          <select name="desserts" value={order.desserts} onChange={handleChange}>
            <option value="">Select Dessert</option>
            <option value="cake">Cake</option>
            <option value="ice-cream">Ice Cream</option>
          </select>
        </div>

        <div className="form-group">
          <label>Soup</label>
          <select name="soup" value={order.soup} onChange={handleChange}>
            <option value="">Select Soup</option>
            <option value="tomato">Tomato Soup</option>
            <option value="chicken">Chicken Soup</option>
          </select>
        </div>

        <button type="submit" className="submit-order-btn">Send Order</button>
      </form>
    </div>
  );
}

export default App;

