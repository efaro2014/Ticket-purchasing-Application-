# Ticket-purchasing-Application-

service_charge = 2
Ticket_price = 10
Tickets_remaining = 100
# run until all the tickets are sold out

def calculate_price(num_tickets):
    return (Ticket_price * num_tickets) + service_charge
while Tickets_remaining >= 1:
    print("the amount of tickets remaining are {}".format(Tickets_remaining))
    name = input('what is your name? ')
    num_tickets = input("how many tickets do you need {} ".format(name))
    try:
        num_tickets = int(num_tickets)
        if num_tickets > Tickets_remaining:
            raise ValueError("there are only {} tickets remaining !".format(Tickets_remaining))
    except ValueError as err:
        print("oh we have an issue, {} please try again ".format(err))
    
    else:
        amount = calculate_price(num_tickets)
        print('the total price is {} '.format(amount))
        should_proceed = input('do you want to proceed? Y/N ')
        if should_proceed.lower() == "y":
           print('sold')
           Tickets_remaining -= num_tickets
           print(" have fun !!")
else:
    print('Thank you {}!'.format(name))


print("sorry all tickets are sold out!")
