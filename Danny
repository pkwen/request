require_relative './game.rb'
require_relative './player.rb'

# create new game instance
g = Game.new
# create new players
player1 = Player.new
player2 = Player.new

# while both players are alive, loop through game logic
while !g.game_over
  # log who's turn it is
  puts g.player1_turn ? "Player 1's turn..." : "Player 2's turn..."
  # generate arithmetic question
  g.ask_q
  # check if correct answer is given
  if g.evaluate_answer
    puts 'Correct.'
  else
    # wrong answer, deduct life from corresponding player
    puts 'Ouch, lost a life.'
    if g.player1_turn
      player1.lose_life
    else
      player2.lose_life
    end
  end
  # alternate turns
  g.player1_turn = !g.player1_turn
  # log score
  puts "Player 1: #{player1.lives} lives left <> Player 2: #{player2.lives} lives left"
  # check if player 1 has run out of lives, if so, toggle game state
  if player1.end_check
    puts 'Game over! Player 2 is the winner.'
    g.game_over = true
  end
  # check if player 2 has run out of lives, if so, toggle game state
  if player2.end_check
    puts 'Game over! Player 1 is the winner.'
    g.game_over = true
  end


end