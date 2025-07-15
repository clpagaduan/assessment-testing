# Technical Assessment - Senior Test Analyst

## Instructions
- As part of our hiring process, we require you to complete a technical assessment.
- This assessment requires the completion of 4 different tasks given below. 
- Please go through the provided repository's README, fork the repository, and then when you're done, please send me a link to your completed GitHub project.
- Please complete all the tasks and send it to me.
_Good luck, have fun and I'm looking forward to seeing the output._

## Task #1
### Using Cypress, write a front end automated script, targeting https://www.harveynorman.com.au where you:

  - Go to https://www.harveynorman.com.au/shokz-opencomm2-uc-usb-a-bone-conduction-stereo-bluetooth-headset.html
  - Add the product to cart
  - Validate that it is in your shopping cart
  - Select a standard delivery method to postcode 2077 ASQUITH and validate the total on cart page

**Additional items:**
This should include any checks along the way that you deem necessary.

**Required Output:**
Once complete, commit your tests, along with any instructions and create a Pull request for it back to this repo

**Answers:**
2025-07-14: Currently blocked on the hCaptcha on the page, preventing me to run scripts. Harvey Norman team needs to do any of the following:
- For best practice, please provide me a url of a staging/test site with the Captcha disabled
- An alternative solution would be to whitelist my IP so that I can test and bypass the captcha
- Please confirm if the test still requires me to use the production site, I can try different workarounds or bypass the hCaptcha but this won't be easy.
Screenshot: https://drive.google.com/file/d/1X-bauxWmtYr7gtkFAvuf8nZBfQ9YnCQR/view?usp=drive_link

## Task #2
### Go to the page - https://www.harveynorman.com.au/lg-65-inch-c5-4k-oled-evo-smart-tv.html and answer the following questions

  1. Identify the request that returns stores when you do stock check for the postcode - 2020
  2. Name the request method for the above request.
  3. Validate if the number of stores displayed to the customer is as per the response.
  
**Required Output:**
Please try to attempt all the questions in Task 2.

**Answer:**
The request URL is GET /svc/sfapi/storeListAndDeliveryCost 
Screenshot:
https://drive.google.com/file/d/1ieb5wBI0VVec7HHbKMEjBRNCSHemdckX/view?usp=sharing

This API is triggered when a user enterse a postcode (e.g. 2020). The postcode is passed as a query param in the request payload.
For the response https://drive.google.com/file/d/1h5iGPd33N_4p61kRSuDMq4oUxz7rkke2/view?usp=drive_link, 
data/soreListAndDeliveryCost/pickup/items I have observed the following:
- The API returns multiple store entries. However, only the first 7 stores are displayed. Flagship Store Auburn, Balgowlah, and Gordon stores are not displayed in the UI despite being in the response.
- I also observed that if the stock_status is "Out of stock", the FE displays "Available soon"


## Task #3
### Go to the page - https://www.harveynorman.com.au/customer/account/create/

You are assigned the task of validating a customer registration form given above. The form includes the following fields with specific requirements:

  1. First Name: Required, must be between 3-10 characters.
  2. Last Name: Required, must be between 3-10 characters.
  3. Email: Required, must be in a valid email format.
  4. Password: Required, must be at least 8 characters, including one uppercase letter, one lowercase letter, one number, and one special character.
  5. Confirm Password: Required, must be same as password.
  6. Terms and Conditions must be accepted before the form submission.
     
**Required Output:**
Write down all possible test cases you would consider for validating this form.

Answer: Please see the test cases here: https://docs.google.com/spreadsheets/d/1NMvbvqCrHoSjClZs2ZYCXyxPRb0aRLYWBgz5oGuAx_I/edit?usp=sharing
Testing considerations:
- Valid/invalid scenarios
- Boundary testing (for character limits)
- Input validation (HTML tags, length, format, special characters)
- UX expectations (e.g. masked passwords, error messages)
- Dependencies (e.g. password confirmations and T&Cs)
- Edge cases like using verified email servers and +1 emails for security purposes
- Also flagged field length rules for first/last names like "Li"

## Task #4
### Analyze the performance of the product listing page using browser DevTools or Lighthouse.

**Instructions:**
1. Navigate to the category page - https://www.harveynorman.com.au/computers-tablets/computers/laptops.
2. Use Chrome DevTools or Lighthouse to measure page load time, render-blocking resources, and Core Web Vitals.
3. Identify any performance bottlenecks, including large image files or unnecessary scripts.
4. Suggest optimizations to improve page performance.

**Required Output:**
Screenshots or JSON report from Lighthouse.
Brief explanation of findings and optimization suggestions.

**Answer:**
- I ran both Lighthouse reports in incongnito and non-incognito and found several differences:
- I suggest having a sit-down session with the FE devs and the PM/Business analyst to help triage what priority optimizations should be done and flag if there are any technical limitations
- Once the optimizations have been applied, create a test plan to make sure that the Lighthouse performance report is better compared to pre-optimization. Flag any existing functionalities that might break.
- Test results: https://drive.google.com/drive/folders/1E5xZCmimfIgD4wraWw5EWjsVTZ4A5euU?usp=drive_link

Incognito:
- Scored 91/100 in Performance
Painpoints:
- LCP Largest Contentful Paint element 1,600 ms for the element div.GelBrickPageHeaderSideMenu_sf-sideMenu_store-context__XDUrl
- Reduce unused JavaScript Est savings of 351 KiB
- Page prevented back/forward cache restoration. "The only actionable failure is Pages with cache-control:no-store header cannot enter back/forward cache"

Non-incognito
- Scored 65/100 in Performance
Painpoints:
- Reduce JavaScript execution time 2.5 s (this is also partially caused by my browser extensions, which should reflect real-world usage of actual users). FE should remove any unused scripts if possible
- Minimize main-thread work 4.3 s. Optimize loading times
- Largest Contentful Paint element 1,300 ms for the element div.GelBrickPageHeaderSideMenu_sf-sideMenu_store-context__XDUrl (same issue with Incognito)
- Page didn't prevent back/forward cache restoration Error

    

