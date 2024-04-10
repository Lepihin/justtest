from random import randint


def arithmetic_progression(a, d, n):
    user_score = 0
    list = []
    for i in range(n):
        list.append(a)
        a += d
    while user_score < 3:
        new_list = list.copy()
        random_number = randint(0, len(list)-1)
        hidden = list[random_number]
        new_list[random_number] = '..'
        progression = ''
        for i in range(0, len(list)):
            progression += str(new_list[i])+' '
        print(progression)
        user_answer = input('Your answer: ')
        if user_answer == str(hidden):
            print('Correct!')
            user_score += 1
    return 'Congratulations!'


print(arithmetic_progression(1, 2, 10))
