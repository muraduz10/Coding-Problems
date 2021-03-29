# Coding-Problems
function cardCounter(array) {
    var count = 0;
    for (var i = 1; i < array.length; i++) {
        var card = array[i];

        if (card.card + i >= 2 && card.card + i <= 6) {
            count++;
        } else if (card.card + i >= 10 || card.card + i === 'face or ace') {
            count--;
        }
        return count;
    }
}

function assertEquals(actual, expected, testDescription) {
    if (actual !== expected) {
        console.log('Test failed:', testDescription);
        return;
    }
    console.log('test passed');
    return;
}

var dealtCards = [ { 'card 0': 2 }, { 'card 1': 6 }, { 'card 2': 8 }, { 'card 3': 'face or ace' } ];

var actual = cardCounter(dealtCards);
var expected = 1;
assertEquals(actual, expected, 'function should return correct HiLo count.');

var dealtCards2 = [ { 'card 0': 'face or ace' }, { 'card 1': 9 }, { 'card 2': 8 }, { 'card 3': 'face or ace' } ];

var actual2 = cardCounter(dealtCards2);
var expected2 = -2;
assertEquals(actual2, expected2, 'function should return correct HiLo count.');
