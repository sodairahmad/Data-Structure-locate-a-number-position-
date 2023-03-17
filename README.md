# Data-Structure-locate-a-number-position-




test = {
    'input': {'cards': [13, 11, 10, 7,7,7,7,7,7, 4, 3,3,3,3,3, 1, 0], 'query': 7}, 'output': 3
}

def test_search(cards, query, mid):
    mid_number = cards[mid]
    if mid_number == query:
        if mid >= 0 and cards[mid+1] ==query:
            return 'left'
        else:
            return 'found'
    elif mid_number < query:
        return 'left'
    elif mid_number > query:
        return 'right'  
     
def locate_card(cards, query):
    lo = 0 
    high = len(cards) - 1 
    print(high)
    while lo <= high:
        mid = (lo + high) // 2 
        result = test_search(cards, query, mid)
        if result ==  'found':
            return mid 
        elif result == 'left':
            high = mid - 1
        elif result == 'right':
            lo = mid + 1
    return -1

print(locate_card(test['input']['cards'], test['input']['query']))

