# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require_relative "config/application"

Rails.application.load_tasks

namespace :monty_hall do
  desc "Run the Monty Hall simulation"
  task :simulate, [:switch, :simulations] do |t, args|
    switch = args[:switch] == 'true'
    simulations = args[:simulations].to_i

    # Пример реализации симуляции
    wins = 0

    simulations.times do
      doors = [1, 0, 0].shuffle
      initial_choice = rand(3)

      if switch
        revealed_index = ([0, 1, 2] - [initial_choice, doors.index(1)]).first
        final_choice = ([0, 1, 2] - [initial_choice, revealed_index]).first

        wins += 1 if doors[final_choice] == 1
      else
        wins += 1 if doors[initial_choice] == 1
      end
    end

    puts "Switching: #{switch}, Simulations: #{simulations}, Wins: #{wins}, Win Rate: #{(wins.to_f / simulations) * 100}%"
  end
end


