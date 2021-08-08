# Duplicate-Encoder
THe goal of this exercise is to convert a string to a new string where each character in the new string is "(" if that character appears only once in the original string, or ")" if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.


Template

    # template
    # def covert (string):
    #     make 2 lists 
    #     list 1 for left bracket
    #     list 2 for left bracket
    #     if character in string doesnt exist in list 1 and 2,  append to list one
    #     if character exists in 2, pass
    #     if charater does exist in list 1 the delete from list 1 and append to list 2

    #     iterate through string and if charector exists in list 1 the "(" else ')'
    
Code

     lftBrac = set()
     rghtBrac = set()

     def duplicate_encode(word):
         word = word.lower()

         for i in word:
             if i not in lftBrac and i not in rghtBrac:
                 lftBrac.add(i)
             elif i in lftBrac:
                 rghtBrac.add(i)
                 lftBrac.discard(i)
         strg=''

         for char in word:
             if char in lftBrac:
                 strg= strg + "("
             else:
                 strg= strg + ")"

         return strg
            
            
run

    print(duplicate_encode('pranav'))
    print(duplicate_encode('sharma'))
    print(duplicate_encode('communication'))
    print(duplicate_encode('notebook'))
    print(duplicate_encode('college'))
    print(duplicate_encode('recede'))


output

    ('(()()(', {'v', 'n', 'r', 'p'}, {'a'})
    ('(()(()', {'h', 'm', 's', 'r'}, {'a'})
    ('))))()))(()))', {'t', 'a', 'u'}, {'c', 'o', 'm', 'n', 'i'})
    ('()((())(', {'k', 'e', 't', 'n', 'b'}, {'o'})
    ('(()))()', {'g', 'c', 'o'}, {'e', 'l'})
    ('()()()', {'c', 'r', 'd'}, {'e'})
            
        
