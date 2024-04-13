# Alt Text Generator

Altext is a Chrome extension designed to improve web accessibility by automatically adding alt attributes to images that lack them. It utilizes BLIP, a service provided by Salesforce, to generate relevant alt text for images on webpages.

## Installation

- Clone the repository:
    ```
    git clone --recursive https://github.com/ota0912/altext.git
    ```
- Install Node Modules:
    ```
    cd Backend && npm install
    ```
- Setting up environment variables:
    - Create a `.env` file referring to `.env.example`.
    - Add your Replicate API token.
- Replace the backend URL in `content.js`.
- Load unpacked extension in the browser.

## Backend

The backend of Altext is built on Express.js and interacts with the [Replicate API for BLIP](https://replicate.com/salesforce/blip) to generate alt text for images.

### Routes

- `/healthcheck` (GET)
- `/generateAlt` (POST) 
    - Request body: `{"image":"<image URL>"}`

## Chrome Extension

The Chrome extension component of Altext is developed using manifest v3. It analyzes the HTML of webpages to identify images without alt attributes and dynamically adds them based on the generated alt text.