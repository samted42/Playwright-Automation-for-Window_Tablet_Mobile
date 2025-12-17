## Test Cases structure for each device type:

tests/
├── desktop/
│   ├── test_homepage.spec.ts
│   ├── test_login.spec.ts
├── tablet/
│   ├── test_products.spec.ts
├── mobile/
    ├── test_cart.spec.ts

## Sample Desktop Test Case (test_homepage.spec.ts)

  import { test, expect } from '@playwright/test';
test.describe('Homepage - Desktop View', () => {
  test('should load the homepage successfully', async ({ page }) => {
    await page.goto('https://automationexercise.com/');
    const title = await page.title();
    expect(title).toBe('Automation Exercise');
  });

  test('should display navigation menu', async ({ page }) => {
    await page.goto('https://automationexercise.com/');
    const navMenu = await page.$('nav'); // Example selector for navigation menu
    expect(navMenu).not.toBeNull();
  });
});  


## Sample Tablet Test Case (test_products.spec.ts)

import { test, expect } from '@playwright/test';

test.use({ viewport: { width: 768, height: 1024 } }); // Tablet resolution
test.describe('Product Page - Tablet View', () => {
  test('should display products correctly on tablet', async ({ page }) => {
    await page.goto('https://automationexercise.com/products');
    const productCards = await page.$$('.product-card'); // Example selector for product cards
    expect(productCards.length).toBeGreaterThan(0);
  });
});


##  Sample Mobile Test Case (test_cart.spec.ts)

import { test, expect } from '@playwright/test';

test.use({ viewport: { width: 375, height: 667 } }); // Mobile resolution

test.describe('Cart Functionality - Mobile View', () => {
  test('should add a product to cart', async ({ page }) => {
    await page.goto('https://automationexercise.com/');
    await page.click('text="Products"'); // Navigate to products page
    await page.click('text="Add to cart"'); // Add a product to cart
    const cartCount = await page.textContent('.cart-count'); // Check cart count (example selector)
    expect(cartCount).toBe('1');
  });
});


## Configuration: playwright.config.ts
- Use the configuration file to specify base URLs, browsers, and reporter formats.

-import { defineConfig } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  timeout: 30000,
  retries: 2,
  reporter: 'html',
  use: {
    baseURL: 'https://automationexercise.com',
    browserName: 'chromium',
    headless: true,
    viewport: { width: 1366, height: 768 },
    screenshot: 'only-on-failure',
    trace: 'on-first-retry',
  },
  projects: [
    { name: 'Desktop - Chrome', use: { browserName: 'chromium' } },
    { name: 'Tablet', use: { viewport: { width: 768, height: 1024 } } },
    { name: 'Mobile', use: { viewport: { width: 375, height: 667 } } },
  ],
});
