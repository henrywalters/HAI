class Bash:
    def __init__(self,computername):
        self.line = ""
        self.words = []
        self.word_count = []
        self.prefix = computername + ":~$ "
        self.reply = ""
    def get_line(self):
        self.line = raw_input(self.prefix)
        self.words = self.line.split(' ')
        self.word_count = len(self.words)
    def memorize(self):
        dic = open("dict.txt", "a+")
        phrase_book = open("phrases.txt","a+")
        with open('dict.txt', "r") as word_list:
            words = word_list.read().split('\n')
        with open("phrases.txt","r") as phrase_list:
            phrases = phrase_book.read().split('\n')

        for i in self.words:
            match = True
            for j in words:
                if i == j:
                    match = False
            if match:
                dic.write(i + "\n")
        match = True
        for i in phrases:
            
            if self.line == i:
                match = False
        if match:
            phrase_book.write(self.line + '\n')

    def think(self):
      
        have_reply = False
        insert_at = 0
        with open('phrases.txt','r') as replie_list:
            phrases = replie_list.read().split('\n')
        for i in range(len(phrases)):
            if (phrases[i] == self.line):
                if ("    " in phrases[i + 1] and i + 1 != len(phrases)):
                    print(phrases[i+1][4:])
                    have_reply = True
                else: insert_at = i
        if not have_reply:
            phrases.insert(insert_at, "    " + self.line)
            replies = open("phrases.txt",'wb+')
            replies.write('\n'.join(phrases))
         
            print (self.line)
                

def run_ai():
    running = True
    while running:
        b = Bash("amelia")
        b.get_line()
        b.memorize()
        b.think()
        
