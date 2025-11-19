Vistora – AI Brand Identity Generator

Vistora is an AI-driven application that automatically generates complete brand identities using text and image generation models. The system processes user inputs to create brand names, taglines, mission statements, color palettes, typography guides, and AI-generated logo concepts.
It is built with Streamlit and integrates OpenAI’s GPT and DALL·E models to deliver end-to-end branding output in a structured format.

Overview

Traditional brand creation requires time, expertise, and design skills. Vistora streamlines this process by using AI to instantly produce a cohesive brand identity aligned with the user’s business idea, target audience, and creative intent.

The application provides:

A structured brand identity document

Automatically extracted color palettes with visual representation

AI-generated logo

A downloadable ZIP brand kit containing all outputs

Vistora is designed for developers, designers, startup founders, and anyone seeking rapid branding support.

Features
1. Brand Identity Text Generation

The system generates:

Brand name

Tagline or slogan

Mission statement

Brand personality and voice

Color palette description

Typography guidance

Logo description for image generation

All text is generated based on the user's selected genre, tone, audience, and description.

2. Color Palette Extraction

The application:

Identifies all valid HEX code patterns from GPT output

Displays colors visually within the UI

Ensures consistency across generated brand assets

3. Logo Creation

A detailed logo prompt created by GPT is passed to the image generation endpoint.
The resulting logo:

Is generated at 1024×1024 resolution

Is previewed inside the app

Is included in the downloadable brand kit

4. ZIP Brand Kit Export

Vistora compiles:

brand_identity.txt (full structured output)

logo.png (AI-generated image)

These are packaged into a ZIP file for download.

5. Interactive Streamlit Interface

Users interact through a clean and minimal Streamlit UI:

Dropdowns for tone and genre

Text-based project description

Real-time loading states

Preview of final brand output

Architecture
Application Flow

User submits brand details through the Streamlit interface.

The application sends the query to GPT for structured brand identity generation.

The text response is parsed for colors, typography, and visual elements.

A refined prompt is created and sent to the image generation endpoint.

The generated logo image is displayed and stored.

A ZIP package is created with all outputs.

Streamlit provides the final download link.

Core Dependencies

Streamlit for UI

Requests for API calls

Pillow for image handling

Python standard libraries: io, base64, zipfile, re

Project Structure
Vistora/
│
├── app.py               # Main application logic
├── requirements.txt     # Python dependencies
├── README.md            # Project documentation
└── .streamlit/
    └── secrets.toml     # API key configuration

Installation
1. Clone the Repository
git clone https://github.com/aayushi-singhhh/Vistora.git
cd Vistora

2. Install Required Packages
pip install -r requirements.txt

3. Configure API Key

Create a file named secrets.toml inside .streamlit/:

.streamlit/secrets.toml


Add your OpenAI key:

OPEN_API_KEY = "your_openai_api_key"

4. Run the Application
streamlit run app.py

Usage Instructions

Open the Streamlit UI in the browser after running the app.

Select or enter:

Brand genre

Tone

Target audience

Brand description

Click the generation button.

Review:

Brand name and tagline

Mission and personality

Color palette

Typography recommendations

Logo description and generated logo

Download the ZIP brand kit.

Technical Details
OpenAI Text Generation

The app uses GPT-based models with a structured prompt that ensures the output follows a consistent brand identity format.
Regular expressions extract only valid color hex values.

OpenAI Image Generation

The logo is generated using the gpt-image-1 or DALL·E endpoint with detailed specifications such as:

Style

Geometry

Color palette

Target audience

Industry tone

The returned base64 image is decoded and displayed.

ZIP Packaging

The ZIP file is created in-memory via:

BytesIO buffer

zipfile.ZipFile with deflated compression

This allows direct download without saving files on disk.

Future Enhancements

Export full brand book in PDF format

Enable multiple logo variations

Add support for vector-style logo output (SVG-like render)

Allow users to select preferred color palette styles

Add session history to track previous brand generations

Provide downloadable typography files

License

This project is licensed under the MIT License.
