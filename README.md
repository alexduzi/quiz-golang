# Math Quiz - Go Edition

A simple command-line math quiz application written in Go that reads questions from a CSV file and tests your arithmetic skills.

## Features

- **CSV-based Questions**: Questions and answers are stored in a `problems.csv` file for easy modification
- **Interactive Quiz**: Presents questions one by one and waits for user input
- **Score Tracking**: Keeps track of correct answers and displays final score
- **Simple Format**: Uses basic addition problems (easily extendable to other operations)

## How It Works

The application reads math problems from `problems.csv`, presents each question to the user, collects their answers, and then calculates and displays the final score.

### File Structure
```
.
├── main.go          # Main application code
└── problems.csv     # Questions and answers database
```

## Getting Started

### Prerequisites
- Go 1.16 or higher installed on your system

### Installation

1. Clone or download the project files
2. Ensure both `main.go` and `problems.csv` are in the same directory
3. Open a terminal in the project directory

### Running the Quiz

```bash
go run main.go
```

## Usage

1. Run the application
2. Answer each math question by typing the number and pressing Enter
3. After all questions are answered, view your final score

### Example Session
```
Question 1: 5+5
10
Question 2: 7+3
10
Question 3: 1+1
2
...
You answered 12 of 13
```

## CSV Format

The `problems.csv` file uses a simple format:
- **Column 1**: The math problem as a string (e.g., "5+5")
- **Column 2**: The correct answer as an integer (e.g., "10")

### Example CSV Content
```csv
5+5,10
7+3,10
1+1,2
8+3,11
```

## Customization

### Adding New Questions
Simply edit the `problems.csv` file:
1. Add new rows with the format: `problem,answer`
2. Save the file
3. Run the quiz again

### Extending Functionality
The code can be easily modified to support:
- Different math operations (subtraction, multiplication, division)
- Multiple choice questions
- Time limits
- Difficulty levels
- Progress saving

## Code Structure

- **File Reading**: Uses `os.ReadFile()` to load the CSV content
- **CSV Parsing**: Leverages Go's built-in `encoding/csv` package
- **User Input**: Captures answers using `fmt.Scanln()`
- **Score Calculation**: Compares user answers with correct answers using maps

## Error Handling

- Handles CSV parsing errors
- Gracefully manages end-of-file conditions
- Uses `log.Fatal()` for critical errors