<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <title>খাবারের দাম</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f7f7f7;
            padding: 40px;
            text-align: center;
        }
        h1 {
            color: #2e7d32;
        }
        #food-list {
            margin: 30px auto;
            max-width: 400px;
            background: #fff;
            padding: 24px;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }
        .food-item {
            display: flex;
            justify-content: space-between;
            margin: 10px 0;
            font-size: 1.1em;
            border-bottom: 1px solid #eee;
            padding-bottom: 8px;
        }
        .food-item:last-child {
            border-bottom: none;
        }
        .food-name {
            color: #555;
        }
        .food-price {
            color: #1b5e20;
            font-weight: bold;
        }
        .total-price {
            margin-top: 20px;
            font-size: 1.15em;
            color: #d84315;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>সব খাবারের তালিকা ও দাম</h1>
    <div id="food-list"></div>

    <script>
        // ৩৫০ টাকার মধ্যে খাবারের তালিকা (নাম এবং দাম)
        const foods = [
            { name: "ভাত", price: ২৫ },
            { name: "ডাল", price: ২০ },
            { name: "মাছ", price: ৬০ },
            { name: "গরুর মাংস", price: ১২০ },
            { name: "মুরগির মাংস", price: ১০০ },
            { name: "সবজি", price: ১৫ },
            { name: "ডিম", price: ১২ },
            { name: "রুটি", price: ৮ },
            { name: "চা", price: ১০ }
        ];

        // মোট দাম গণনা ফাংশন
        function totalPrice() {
            let sum = 0;
            foods.forEach(food => sum += food.price);
            return sum;
        }

        // HTML-এ দেখানোর ফাংশন
        function displayFoods() {
            const foodList = document.getElementById('food-list');
            foods.forEach(food => {
                const div = document.createElement('div');
                div.className = 'food-item';
                div.innerHTML = `
                    <span class="food-name">${food.name}</span>
                    <span class="food-price">${food.price} টাকা</span>
                `;
                foodList.appendChild(div);
            });

            // মোট দাম দেখানো
            const totalDiv = document.createElement('div');
            totalDiv.className = 'total-price';
            totalDiv.innerHTML = `মোট দাম: ${totalPrice()} টাকা`;
            foodList.appendChild(totalDiv);
        }

        // পেজ লোড হলে খাবার দেখাও
        displayFoods();
    </script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background: #f7f7f7;
    padding: 40px;
    text-align: center;
}
h1 {
    color: #2e7d32;
}
#food-list {
    margin: 30px auto;
    max-width: 400px;
    background: #fff;
    padding: 24px;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}
.food-item {
    display: flex;
    justify-content: space-between;
    margin: 10px 0;
    font-size: 1.1em;
    border-bottom: 1px solid #eee;
    padding-bottom: 8px;
}
.food-item:last-child {
    border-bottom: none;
}
.food-name {
    color: #555;
}
.food-price {
    color: #1b5e20;
    font-weight: bold;
}
// ৩৫০ টাকার মধ্যে খাবারের তালিকা (নাম এবং দাম)
const foods = [
    { name: "ভাত", price: ২৫ },
    { name: "ডাল", price: ২০ },
    { name: "মাছ", price: ৬০ },
    { name: "গরুর মাংস", price: ১২০ },
    { name: "মুরগির মাংস", price: ১০০ },
    { name: "সবজি", price: ১৫ },
    { name: "ডিম", price: ১২ },
    { name: "রুটি", price: ৮ },
    { name: "চা", price: ১০ },
];

// মোট দাম দেখানোর জন্য ফাংশন
function totalPrice() {
    let sum = 0;
    foods.forEach(food => sum += food.price);
    return sum;
}

// HTML-এ দেখানোর জন্য ফাংশন
function displayFoods() {
    const foodList = document.getElementById('food-list');
    foods.forEach(food => {
        const div = document.createElement('div');
        div.className = 'food-item';
        div.innerHTML = `
            <span class="food-name">${food.name}</span>
            <span class="food-price">${food.price} টাকা</span>
        `;
        foodList.appendChild(div);
    });

    // মোট দাম দেখানো
    const totalDiv = document.createElement('div');
    totalDiv.style.marginTop = '20px';
    totalDiv.innerHTML = `<strong>মোট দাম: ${totalPrice()} টাকা</strong>`;
    foodList.appendChild(totalDiv);
}

// পেজ লোড হলে ডাটা দেখাও
displayFoods();
