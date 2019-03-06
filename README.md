# PokeKai

Website Brainstorming

Okay, this is the repository for the restaurant website of Poke Kai.
Poke Kai is a new restaurant that serves Poke, a trending dish that is typically composed of fresh fish, veggies, rice, and sauce. 
The store is located in Pennsylvania near Dorney Park in Allentown. Exact Address --> XXXXX

Wait, are they hiring someone for the website? Even so, I should make it as a replacement.

I need icons, images, etc.

Need mobile compatibility, which means --> React Native? Hard.

What exactly is the plan for building this website? What does it need?

&&& Relatively easier than other parts. Relies almost completely on front end stuff. Be aware that we need to keep track of the login state. If the user is logged in, the landing page and other options will be different. For instance, there won't be a sign up button if you're already logged in, instead there would be a logout button and a profile expander.
- Responsive Landing Page.
    - Navbar, one part static, another specifically when at top.
        - Learn how to do drop down menus on hover navbar divs.
    - Stylized using the standard div blocks going down. 
        - Adjust each div block into sections depending on purpose.
        - Use y-transition to make animation overlap between div sections
    - Perhaps the first thing is a slideshow section.

&&& Again only front end stuff with links. Maybe some trouble with animating it fluidly.
- Sidebar with important links
    - If you click on it, it opens up from the left.
    - Should be present for most pages excluding landing page, checkout, etc.

&&& Requires some database work that I'm not totally confident in. Also needs an automated way to send confirmation and reset emails to those who register. Again, another difficult task.
- Personalized Accounts.
    - Login should be email and password.
        - How to verify if the email exists? Does it really matter if we automatically verify right after?
        - Should have a way to send confirmation email to verify account.
        - Two separate pages for account creation and log in.
            - Or if you're fancy make it switch between two divs that overlap.
        - Should have a forgot password option that sends reset password option to registered email. Assumes the email is secure. Should only be linked to Sign In page.
    - Requires login page which means we need a database to access information like username, password, saved addresses, profile stuff.
    - Profile page for user info.
        - Ability to edit info and save to database.
        - first name, last name, phone number, etc.
    - Have order history which means you need a status state...
        - Or you can leave it as purely informational.

&&& These are just links. Make it elegant but reserved. Only for business stuff.
- Footer
    - Should be a relatively small section that is applied to every page.
    - Line where we specify company rights, privacy policy, legal stuff, etc.
        - Cookie policy?
    - Have two/three divs for contact, help, social media, about, hiring, logos, blog, etc.
    - Have a feedback option for improvement.

&&& Requires server work because it sends the menu item and any modifiers to the shopping cart. Shopping cart needs to keep track of that so I'm pretty sure you need some database work for that. Having a sorting function seems like quite a lot of work.
- Menu
    - Should be a direct link from the navbar.
    - I'm thinking of doing a setup that has tabs to classify dishes. Under each tab we list all the dishes that satisfy the classification.
    - The dishes will have a title and a short description.
    - Have an add button. If you click that, a pop up comes up.
        - Pop up is to specify modifications, quantity, special instructions, etc.
    - After submitting popup, it should go to a shopping cart.
    - Add a sorting function.
        - I was thinking sort by popularity, rating, and price. Maybe trending but that seems complicated.
        - So accounts need to provide ratings for these things to work. We also need to keep track of how many dishes were actually ordered for popularity. Price is easy though. Might sort by price, then alphabetic? Or just ignore it.
        - Setting up a rating system seems really complicated.
    - Menu section can be one really long scroll. The menu headers are just shortcuts to those sections. DoorDash does this pretty elegantly.

&&& Probably the most difficult part. I really don't know how to do the server side stuff for this. Also understand how each item is represented as an object can get hairy. For instance, some items may have special modifiers and I need to tie a price amount to that. I need that price amount for total calculation but I don't know how to access that.
- Shopping Cart
    - You need to sustain this shopping cart array where ever you go because we don't want to erase the items already added on.
    - Checkout should clear it.
    - I'm guessing the array elements are composed of objects that have the title, price, modifiers. How do you consider specific options? Set null?
    - You have to calculate price, but also consider extra costs from modifiers, delivery, etc.
    - Definitely need server side work for this.
    - I'm thinking of setting it as slim div on the right side.
    - Should be a scroll function if overflow y.
    - Should have a remove button that deletes from the shopping cart array.

&&& Lot of setup stuff that can cause problems. What exactly happens when someone places an order? How do we send that information to the restaurant in a suitable format? How does the restaurant comply with this?
- Checkout
    - We need multiple sections including address if delivery, payment options, scheduling, summary, and total.
    - Payment options
        - Two possible options. Cash or Credit. Cash is easy, just pay there. Credit card becomes complicated. I need to verify that the credit card is legit and know how to process that. I think there are some npm packages for that but I don't know how to set that up. I think you need a bank account to transfer it into? What happens if it returns declined?
    - Delivery address
        - The problem with this is that we have a requirement to avoid addresses that are too far. How do I calculate the distance between the store and the specified address? I need some package for that. I can't even imagine how that would work.
        - Add special instructions for driver.
    - Total Calculation
        - Need to consider item prices with modifiers, coupons, delivery tip, tax, etc.
    - Place Order
        - There needs to be a kick back if any of the sections are not filled in.
        - Once that button is clicked, we need to send that information to the restaurant in the form of a receipt. So what type of file is that? Do we automatically print a receipt? How does that work?

