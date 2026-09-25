# Reflection

## Technical Reflection

**1. Layout and Structure**

At first the image sat on top of the text and everything was pushed to the left, so the page felt empty and unbalanced. We needed the image and details side by side and the card centered. Flexbox made sense because it's only two items in one row. We used display: flex with gap for the spacing and margin: 0 auto with a max-width to center the card. We didn't need floats or fixed positioning.

**2. Visual Hierarchy and Spacing**

Making the price bigger, bold, and red made the biggest difference. Before, the price looked the same as the description. Now it's the first thing you notice after the product name. We picked red because it stands out against the black and gray text and is common for prices in online stores.

**3. Interaction Design**

We made the button solid black so it's the heaviest, most noticeable thing on the card. The wide padding makes it easy to click. On hover it turns gray and grows a little, so the user knows it's clickable. If the button looked like plain text, people might skip past it, which would lower Add-to-Cart.

**4. Responsiveness and Robustness**

Below 768px the card switches to flex-direction: column, so the image goes on top. The padding also gets smaller and the button becomes full width, so it's easier to tap with a thumb. Since we only used classes and shared variables, 30 cards would look the same as 3.

## Business Reflection

**5. Conversion Impact**

We mainly wanted more clicks on Add to Cart by making the page faster to scan. The order goes product name, price, short description, then the button. A shopper can decide quickly and the button is right there when they do.

**6. Revenue and Risk Thinking**

We would test the button first, since it's the thing directly connected to the metric. We could try a different color or move it closer to the price. If that doesn't help, the problem might be trust instead of design. Then we would test adding real product photos, reviews, or shipping info near the button.
