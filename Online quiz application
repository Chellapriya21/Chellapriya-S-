class Question:
    def __init__(self, text, choices, answer):
        self.text = text            # Question text
        self.choices = choices      # List of answer choices
        self.answer = answer        # Index of correct answer in choices (0-based index)

    def check_answer(self, user_answer):
        return self.choices[user_answer] == self.choices[self.answer]


class Quiz:
    def __init__(self, questions):
        self.questions = questions  # List of Question objects
        self.score = 0              # Initialize score to zero
        self.total_questions = len(questions)

    def conduct_quiz(self):
        for question in self.questions:
            print(question.text)
            for i, choice in enumerate(question.choices):
                print(f"{i + 1}. {choice}")
            user_answer = self.get_user_input()
            if question.check_answer(user_answer):
                print("Correct!")
                self.score += 1
            else:
                print("Incorrect.")

    def get_user_input(self):
        while True:
            try:
                user_input = int(input("Enter your answer (1, 2, 3, etc.): ")) - 1
                if 0 <= user_input < len(self.questions[0].choices):
                    return user_input
                else:
                    print("Invalid input. Please enter a valid option.")
            except ValueError:
                print("Invalid input. Please enter a number.")

    def display_result(self):
        print(f"You scored {self.score} out of {self.total_questions}.")

    def start(self):
        print("Welcome to the Java Basics Quiz!")
        input("Press Enter to start...")
        self.conduct_quiz()
        self.display_result()


# Example usage:
if __name__ == "__main__":
    # Sample questions
    questions = [
        Question("What is Java?", ["A programming language", "A fruit", "A car"], 0),
        Question("Which keyword is used for inheritance in Java?", ["inherit", "extends", "implements"], 1),
        Question("What is the output of 2 + 2 in Java?", ["4", "5", "6"], 0),
    ]

    # Create a quiz object and start the quiz
    quiz = Quiz(questions)
    quiz.start() 
