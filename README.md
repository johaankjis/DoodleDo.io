# AI-Powered Calculator with Drawing Recognition

This project is an interactive calculator that allows users to draw math problems and receive real-time solutions. It integrates the **Gemini Flash AI API** to recognize hand-drawn equations, with a **Python backend** for processing and a **React frontend** to create a smooth, user-friendly interface.

## Features

- **Hand-drawn Math Recognition**: Users can draw equations on a canvas, and the AI will recognize and solve the problem in real-time.
- **Gemini Flash AI API Integration**: Leveraging the power of AI to interpret and calculate hand-drawn input.
- **Interactive Frontend**: Built with React for a responsive and dynamic user interface.
- **Real-time Calculations**: Receive immediate feedback and results as you draw your equations.

## Project Structure
/frontend
/src
- App.js        # Main React component
- Canvas.js     # Drawing canvas component
- Result.js     # Displays real-time results
/backend
/app
- api.py        # Python backend logic, handles API calls to Gemini Flash AI
- routes.py     # Backend routes for handling user input and sending requests
- requirements.txt   # Backend dependencies
README.md

## Getting Started

### Prerequisites

- **Python 3.8+**
- **Node.js** and **npm**
- Gemini Flash AI API key

### Setup Instructions

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/ai-drawing-calculator.git
    cd ai-drawing-calculator
    ```

2. **Backend Setup**:

    - Navigate to the backend directory:
      ```bash
      cd backend
      ```
    - Install dependencies:
      ```bash
      pip install -r requirements.txt
      ```
    - Set up your environment variables for the **Gemini Flash AI API**.
    - Start the backend server:
      ```bash
      python api.py
      ```

3. **Frontend Setup**:

    - Navigate to the frontend directory:
      ```bash
      cd frontend
      ```
    - Install dependencies:
      ```bash
      npm install
      ```
    - Start the frontend:
      ```bash
      npm start
      ```

4. **Access the Application**:

    - Open your browser and go to `http://localhost:3000` to use the AI-powered calculator.

## Usage

1. Draw your equation using the canvas on the screen.
2. The AI will recognize the drawn input and compute the result in real-time.
3. The calculated result will be displayed below the canvas.

## Technologies Used

- **Python**: Backend logic and API integration.
- **React**: Frontend framework for creating an interactive user interface.
- **Gemini Flash AI API**: AI-powered recognition of hand-drawn math problems.
- **Flask**: For serving the backend API.

## Challenges

Some key challenges included:
- Accurate AI recognition of hand-drawn math equations.
- Real-time communication between the backend and frontend.
- Managing React state efficiently for real-time updates.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request.

## License

This project is licensed under the MIT License.

## Acknowledgments

- Thanks to the **Gemini Flash AI API** for providing the AI capabilities.
- Inspired by the potential to integrate AI into educational tools.
