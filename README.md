# Technical Assessment - Senior Test Analyst

## Instructions
- As part of our hiring process, we require you to complete a technical assessment.
- This assessment requires the completion of 4 different tasks given below. 
- Please go through the provided repository's README, fork the repository, and then when you're done, please send me a link to your completed GitHub project.
- Please also note, you have one week, from the date you received this link in email, to complete all the tasks and send it to me.
_Good luck, have fun and I'm looking forward to seeing the output._

## Task #1
### Using Cypress, write a front end automated script, targeting https://www.harveynorman.com.au where you:

  - Go to https://www.harveynorman.com.au/shokz-opencomm2-uc-usb-a-bone-conduction-stereo-bluetooth-headset.html
  - Add the product to cart
  - Validate that it is in your shopping cart
  - Select a schedule delivery method to postcode 2077 ASQUITH and validate the total on cart page (in case schedule delivery does not show, you can use standard delivery)

**Additional items:**
This should include any checks along the way that you deem necessary.

**Required Output:**
Once complete, commit your tests, along with any instructions and create a Pull request for it back to this repo

## Task #2
### Go to the page - https://www.harveynorman.com.au/lg-65-inch-c5-4k-oled-evo-smart-tv.html and answer the following questions

  1. Identify the request that returns stores when you do stock check for the postcode - 2020
  2. Name the request method for the above request.
  3. Validate if the number of stores displayed to the customer is as per the response.
  
**Required Output:**
Please try to attempt all the questions in Task 2.

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
    

