#exp2_9538_magicsquare
import random

class TicTacToe:
    def __init__(self):
        self.board = [' ' for _ in range(9)]  # Representing the Tic-Tac-Toe board

    def available_moves(self):
        return [i for i, spot in enumerate(self.board) if spot == ' ']

    def empty_squares(self):
        return ' ' in self.board

    def num_empty_squares(self):
        return self.board.count(' ')

    def make_move(self, square, letter):
        self.board[square] = letter

    def print_board(self):
        for row in [self.board[i * 3:(i + 1) * 3] for i in range(3)]:
            print('| ' + ' | '.join(row) + ' |')

class Player:
    def __init__(self, letter):
        self.letter = letter

    def get_move(self, game):
        pass

class HumanPlayer(Player):
    def get_move(self, game):
        valid_square = False
        val = None
        while not valid_square:
            square = input(self.letter + '\'s turn. Input move (0-8): ')
            try:
                val = int(square)
                if val not in game.available_moves():
                    raise ValueError
                valid_square = True
            except ValueError:
                print('Invalid square. Try again.')
        return val

class RandomComputerPlayer(Player):
    def get_move(self, game):
        square = random.choice(game.available_moves())
        return square

def play(game, x_player, o_player, print_game=True):
    if print_game:
        game.print_board()

    letter = 'X'  # Starting letter
    while game.empty_squares():
        if letter == 'O':
            square = o_player.get_move(game)
        else:
            square = x_player.get_move(game)

        if game.board[square] == ' ':
            game.make_move(square, letter)
            if print_game:
                print(letter + f' makes a move to square {square}')
                game.print_board()
                print('')  # Empty line

            if game.num_empty_squares() == 0:
                print('It\'s a tie!')
                return

            if game.winner(square, letter):
                print(letter + ' wins!')
                return

            letter = 'O' if letter == 'X' else 'X'  # Switch player

        if print_game:
            print('The game is a tie!')

if __name__ == '__main__':
    x_player = HumanPlayer('X')
    o_player = RandomComputerPlayer('O')
    t = TicTacToe()
    play(t, x_player, o_player, print_game=True)
OUTPUT:
Welcome to Tic Tac Toe!
  |   |  
-------------
  |   |  
-------------
  |   |  
-------------
Enter your move (1-9):  5
  |   |  
-------------
  | X |  
-------------
  |   |  
-------------
Computer chooses position 8
  |   |  
-------------
  | X |  
-------------
  | O |  
-------------
Enter your move (1-9):  7
  |   |  
-------------
  | X |  
-------------
X | O |  
-------------
Computer chooses position 3
  |   | O
-------------
  | X |  
-------------
X | O |  
-------------
Enter your move (1-9):  1
X |   | O
-------------
  | X |  
-------------
X | O |  
-------------
Computer chooses position 4
X |   | O
-------------
O | X |  
-------------
X | O |  
-------------
Enter your move (1-9):  4
ERROR! That position is already taken. Choose a different one.
Enter your move (1-9):  9
X |   | O
-------------
O | X |  
-------------
X | O | X
-------------
X wins!
