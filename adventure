from data import locations

directions = {
    'west': (-1, 0),
    'east': (1, 0),
    'north': (0, -1),
    'south': (0, 1),
}

position = (0, 0)

items = ['wallet']

while True:
    location = locations[position]
    print 'You are at the %s.' % location['title']
    print location['description']
    if location['item'] not in items:
        print 'You can see a %s.' % location['item']
    print 'Inventory: %s' % items

    valid_directions = {}
    for k, v in directions.iteritems():
        possible_position = (position[0] + v[0], position[1] + v[1])
        possible_location = locations.get(possible_position)
        if possible_location:
            print 'to the %s is a %s' % (k, possible_location['title'])
            valid_directions[k] = possible_position

    user_input = raw_input('which direction do you want to go, or which item do you want to take?\n')
    if location['item'] == user_input and location['item'] not in items:
        print "%s taken. Which direction now?" % user_input
        items.append(location['item'])
    elif user_input in directions:
        new_position = valid_directions.get(user_input)
        if new_position:
            position = new_position
        else:
            print "Sorry, that isn't a valid direction."
    else:
        print "Sorry, I don't understand."
