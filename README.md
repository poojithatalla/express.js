# express.js
new repository
const express = require('express');
const app = express();

// Middleware to parse JSON request body
app.use(express.json());

// POST /register route
app.post('/register', (req, res) => {
    const { name, email, password } = req.body;

    if (!name || !email || !password) {
        return res.status(400).json({ message: 'All fields are required' });
    }

    // Process the data (e.g., save to database)
    // Here, we just send a success message for simplicity

    res.status(200).json({ message: 'Registration successful' });
});

// Start the server
app.listen(3000, () => {
    console.log('Server running on port 3000');
});
