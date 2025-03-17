class QuizGame:
    def __init__(self):
        self.questions = [
            {
                "question": "What is the capital of France?",
                "options": ["A. Paris", "B. London", "C. Berlin", "D. Madrid"],
                "answer": "A"
            },
            {
                "question": "Which planet is known as the Red Planet?",
                "options": ["A. Earth", "B. Mars", "C. Jupiter", "D. Saturn"],
                "answer": "B"
            },
            {
                "question": "Who wrote 'Romeo and Juliet'?",
                "options": ["A. Charles Dickens", "B. William Shakespeare", "C. Mark Twain", "D. Jane Austen"],
                "answer": "B"
            },
            {
                "question": "What is the largest ocean on Earth?",
                "options": ["A. Atlantic Ocean", "B. Indian Ocean", "C. Arctic Ocean", "D. Pacific Ocean"],
                "answer": "D"
            },
            {
                "question": "Which element has the chemical symbol 'O'?",
                "options": ["A. Oxygen", "B. Gold", "C. Silver", "D. Iron"],
                "answer": "A"
            }
        ]
        self.score = 0

    def display_question(self, question_data):
        print(question_data["question"])
        for option in question_data["options"]:
            print(option)
        user_answer = input("Your answer (A/B/C/D): ").strip().upper()
        return user_answer

    def check_answer(self, user_answer, correct_answer):
        if user_answer == correct_answer:
            print("Correct!\n")
            self.score += 1
        else:
            print(f"Wrong! The correct answer is {correct_answer}.\n")

    def run_quiz(self):
        print("Welcome to the Quiz Game!\n")
        for question in self.questions:
            user_answer = self.display_question(question)
            self.check_answer(user_answer, question["answer"])
        
        print(f"Quiz ended! Your final score is {self.score}/{len(self.questions)}.")
        if self.score == len(self.questions):
            print("Congratulations! You got all the answers correct!")
        elif self.score >= len(self.questions) / 2:
            print("Good job! You passed the quiz.")
        else:
            print("Better luck next time!")

if __name__ == "__main__":
    game = QuizGame()
    game.run_quiz()
