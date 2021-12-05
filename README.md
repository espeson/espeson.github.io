## Welcome to espeson's personal webpage

Welcome! I’m an undergraduate student at Duke Kunshan University and a student worker at Environmental Research Center. Before coming to DKU, I was a student at Suzhou High School Affiliated to Xi’an Jiaotong University.


### Coder

I'm trying to write code in Python and Java. Here is my proudest piece of code.

```markdown
from mazegeneration import *

MG = Maze_Generator(40, 10)
MG.create_maze()
class Queue():
    def __init__(self):
        self.path = []

    def enqueue(self, n):
        self.path.append(n)

    def dequeue(self):
        n = self.path[0]
        self.path = self.path[1:]
        return n

def neighbour(step):
    neighbour = []
    if step.north != None:
        neighbour.append(step.north)
    if step.south != None:
        neighbour.append(step.south)
    if step.east != None:
        neighbour.append(step.east)
    if step.west != None:
        neighbour.append(step.west)
    return neighbour


def BFS(graph, start, end):
    Q = Queue()

    path = [start]
    Q.enqueue(path)

    while True:
        cur_path = Q.dequeue()
        last_step = cur_path[-1]

        if last_step == end:
            return cur_path

        for point in neighbour(last_step):
            if point not in cur_path:
                Q.enqueue(cur_path + [point])
    return None


index=0
while index <len(BFS(MG, MG.START, MG.END))-1:
    MG.draw_line(BFS(MG, MG.START, MG.END)[index], BFS(MG, MG.START, MG.END)[index + 1])
    index+=1

```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/espeson/espeson.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
