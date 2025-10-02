# DoodleDo.io

An AI-powered interactive drawing calculator that recognizes hand-drawn mathematical expressions, equations, and graphical problems, providing real-time solutions. Built with the **Gemini 1.5 Flash AI API** for intelligent recognition, **FastAPI** backend for processing, and a modern **React + TypeScript** frontend with **Vite**.

## Features

- **Hand-drawn Math Recognition**: Draw equations, expressions, or mathematical diagrams on an interactive canvas and get instant AI-powered solutions
- **Multi-type Problem Support**:
  - Simple mathematical expressions (2 + 2, 3 * 4, etc.)
  - Equations with variables (x² + 2x + 1 = 0)
  - Variable assignments (x = 5, y = 10)
  - Graphical math problems (geometry, trigonometry, word problems)
  - Abstract concept detection (visual representations of ideas)
- **Variable Memory**: Assign and reuse variables across multiple calculations
- **Interactive Canvas**: Draw with multiple colors using an intuitive drawing interface
- **Real-time LaTeX Rendering**: Mathematical expressions are rendered beautifully using MathJax
- **Draggable Results**: Move calculation results anywhere on the canvas
- **Responsive UI**: Modern interface built with Mantine and Tailwind CSS

## Project Structure

```
DoodleDo.io/
├── src/                          # Frontend source code
│   ├── screens/
│   │   └── home/
│   │       └── index.tsx         # Main canvas and drawing interface
│   ├── components/
│   │   └── ui/
│   │       └── button.tsx        # Reusable UI components
│   ├── App.tsx                   # Main React component with routing
│   ├── main.tsx                  # Application entry point
│   └── constants.ts              # Color swatches and constants
├── back/                         # Backend source code
│   ├── apps/
│   │   └── calculator/
│   │       ├── route.py          # FastAPI routes for image processing
│   │       └── utils.py          # Gemini AI integration logic
│   ├── main.py                   # FastAPI application setup
│   ├── constants.py              # Server configuration
│   ├── schema.py                 # Pydantic models
│   └── requirements.txt          # Python dependencies
├── package.json                  # Node.js dependencies
├── vite.config.ts                # Vite configuration
├── tsconfig.json                 # TypeScript configuration
└── README.md
```

## Getting Started

### Prerequisites

- **Python 3.8+** with pip
- **Node.js 16+** and **npm**
- **Gemini API Key** (Get one from [Google AI Studio](https://aistudio.google.com/))

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/johaankjis/DoodleDo.io.git
   cd DoodleDo.io
   ```

2. **Backend Setup**:

   - Navigate to the backend directory:
     ```bash
     cd back
     ```
   
   - Install Python dependencies:
     ```bash
     pip install -r requirements.txt
     ```
   
   - Create a `.env` file in the `back` directory and add your Gemini API key:
     ```bash
     GEMINI_API_KEY=your_api_key_here
     ```
   
   - Start the FastAPI server:
     ```bash
     python main.py
     ```
   
   The backend server will run on `http://localhost:8900`

3. **Frontend Setup**:

   - Open a new terminal and navigate to the project root directory:
     ```bash
     cd DoodleDo.io
     ```
   
   - Install Node.js dependencies:
     ```bash
     npm install
     ```
   
   - Create a `.env` file in the root directory and configure the API URL:
     ```bash
     VITE_API_URL=http://localhost:8900
     ```
   
   - Start the development server:
     ```bash
     npm run dev
     ```
   
   The frontend will run on `http://localhost:5173` (or the port shown in the terminal)

4. **Access the Application**:

   Open your browser and navigate to the URL shown in your terminal (typically `http://localhost:5173`)

## Usage

1. **Select a Color**: Choose from the color palette at the top of the screen
2. **Draw**: Click and drag on the canvas to draw your mathematical expression or diagram
3. **Calculate**: Click the "Calculate" button to send your drawing to the AI
4. **View Results**: The AI will analyze your drawing and display the result with LaTeX formatting
5. **Assign Variables**: Draw variable assignments (like `x = 5`) to use them in later calculations
6. **Reset**: Click the "Reset" button to clear the canvas and start over

### Example Use Cases

- **Simple Math**: Draw `2 + 3 * 4` and get `14`
- **Equations**: Draw `x² + 2x + 1 = 0` to solve for x
- **Variables**: Draw `x = 5`, then draw `2x + 3` to get `13`
- **Geometry**: Draw a triangle with measurements for area/perimeter calculations
- **Concepts**: Draw symbolic representations (heart for love, etc.)

## Technologies Used

### Frontend
- **React 18** with **TypeScript**: Modern UI framework with type safety
- **Vite**: Fast build tool and development server
- **Mantine UI**: Component library for consistent design
- **Tailwind CSS**: Utility-first CSS framework
- **MathJax**: Beautiful mathematical notation rendering
- **Axios**: HTTP client for API communication
- **React Draggable**: Interactive draggable components

### Backend
- **FastAPI**: Modern, fast Python web framework
- **Uvicorn**: ASGI server for FastAPI
- **Google Generative AI (Gemini 1.5 Flash)**: AI model for image analysis
- **Pillow**: Image processing library
- **Pydantic**: Data validation using Python type annotations

### AI Integration
- **Gemini 1.5 Flash API**: Advanced vision model for recognizing hand-drawn content

## API Reference

### POST `/calculate`

Analyzes a hand-drawn image and returns mathematical results.

**Request Body**:
```json
{
  "image": "data:image/png;base64,<base64_encoded_image>",
  "dict_of_vars": {
    "x": "5",
    "y": "10"
  }
}
```

**Response**:
```json
{
  "message": "Image processed",
  "status": "success",
  "data": [
    {
      "expr": "2 + 3",
      "result": "5",
      "assign": false
    }
  ]
}
```

## Development

### Running in Development Mode

Both frontend and backend support hot-reloading for development:

```bash
# Frontend (from project root)
npm run dev

# Backend (from back directory)
python main.py  # Runs with reload=True in dev mode
```

### Building for Production

```bash
# Frontend
npm run build

# Production build will be in dist/ directory
npm run preview  # Preview production build
```

### Linting

```bash
npm run lint
```

## Challenges & Solutions

Key technical challenges addressed in this project:

- **AI Recognition Accuracy**: Implementing comprehensive prompts with the Gemini API to handle multiple problem types (equations, diagrams, concepts)
- **Canvas State Management**: Efficiently managing drawing state, variable storage, and real-time updates in React
- **Image Processing**: Converting canvas drawings to base64 and processing them through the AI pipeline
- **LaTeX Rendering**: Integrating MathJax for beautiful mathematical notation display
- **CORS & API Communication**: Setting up FastAPI middleware for seamless frontend-backend communication
- **Type Safety**: Implementing TypeScript interfaces for robust data handling

## Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

Please ensure your code follows the existing style and includes appropriate documentation.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- **Google Gemini AI Team** for providing the powerful Gemini 1.5 Flash API
- **MathJax** for excellent mathematical notation rendering
- **Mantine** and **Tailwind CSS** for the beautiful UI components
- Inspired by the potential to make mathematics more accessible through AI and visual interfaces

## Troubleshooting

**Backend not starting?**
- Ensure you have Python 3.8+ installed
- Check that your `.env` file has a valid `GEMINI_API_KEY`
- Verify all dependencies are installed: `pip install -r requirements.txt`

**Frontend not connecting?**
- Ensure the backend is running on `http://localhost:8900`
- Check that `VITE_API_URL` in your `.env` file matches the backend URL
- Clear browser cache and restart the dev server

**Drawing not working?**
- Ensure JavaScript is enabled in your browser
- Check browser console for any errors
- Try a different browser (Chrome/Firefox recommended)
