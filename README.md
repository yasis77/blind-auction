# blind-auction

from replit import clear
#HINT: You can call clear() to clear the output in the console.
from art import logo

print(logo)

bids = {}
bidding_finished = False

def find_highest_bidder(bidding_record):
  highest_number = 0
  for bidder in bidding_record:
    bid_amount = bidding_record[bidder]
    if bid_amount > highest_number:
      highest_number = bid_amount
      winner = bidder
  print(f"the winner is {winner} with a bid of ${highest_number}")

while not bidding_finished:
  name = input("what is your name?: ")
  price = int(input("what is your bid? $"))
  bids[name] = price
  should_continue = input("are there any other bidders? type 'yes' or 'no'")
  if should_continue == "no":
    bidding_finished = True
    find_highest_bidder(bids)
  elif should_continue == "yes":
    clear()

