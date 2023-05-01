#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

class Game {
public:
    enum class Choice { ROCK = 1, PAPER, SCISSORS };
    enum class Result { WIN, LOSE, TIE };

    Game() {
        srand(static_cast<unsigned int>(time(nullptr)));
    }

    Choice getUserChoice() const {
        int userChoice;
        cout << "Please enter your choice (1 for Rock, 2 for Paper, 3 for Scissors): ";
        cin >> userChoice;
        return static_cast<Choice>(userChoice);
    }

    Choice getComputerChoice() const {
        int computerChoice = rand() % 3 + 1;
        return static_cast<Choice>(computerChoice);
    }

    Result play(Choice userChoice, Choice computerChoice) const {
        if (userChoice == computerChoice) {
            return Result::TIE;
        }
        else if ((userChoice == Choice::ROCK && computerChoice == Choice::SCISSORS) ||
                 (userChoice == Choice::PAPER && computerChoice == Choice::ROCK) ||
                 (userChoice == Choice::SCISSORS && computerChoice == Choice::PAPER)) {
            return Result::WIN;
        }
        else {
            return Result::LOSE;
        }
    }

    void printResult(Result result) const {
        if (result == Result::WIN) {
            cout << "You win!\n";
        }
        else if (result == Result::LOSE) {
            cout << "You lose.\n";
        }
        else {
            cout << "It's a tie.\n";
        }
    }
};

int main() {
    Game game;
    Game::Choice userChoice, computerChoice;
    Game::Result result;

    cout << "Welcome to Rock Paper Scissors game!\n";
    userChoice = game.getUserChoice();
    computerChoice = game.getComputerChoice();
    result = game.play(userChoice, computerChoice);
    game.printResult(result);

    return 0;
}
