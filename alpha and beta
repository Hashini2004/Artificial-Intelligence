class MiniMax:
    def __init__(self, game_tree):
        self.game_tree = game_tree
        self.root = game_tree.root  
        self.currentNode = None    
        self.successors = []
        return

    def minimax(self, node):
        best_val = self.max_value(node) 
        successors = self.getSuccessors(node)
        print "MiniMax:  Utility Value of Root Node: = " + str(best_val)
        best_move = None
        for elem in successors: 
            if elem.value == best_val:
                best_move = elem
                break
        return best_move
    def max_value(self, node):
        print "MiniMax–>MAX: Visited Node :: " + node.Name
        if self.isTerminal(node):
            return self.getUtility(node)

        infinity = float('inf')
        max_value = –infinity

        successors_states = self.getSuccessors(node)
        for state in successors_states:
            max_value = max(max_value, self.min_value(state))
        return max_value

    def min_value(self, node):
        print "MiniMax–>MIN: Visited Node :: " + node.Name
        if self.isTerminal(node):
            return self.getUtility(node)

        infinity = float('inf')
        min_value = infinity

        successor_states = self.getSuccessors(node)
        for state in successor_states:
            min_value = min(min_value, self.max_value(state))
        return min_value
    def getSuccessors(self, node):
        assert node is not None
        return node.children
    def isTerminal(self, node):
        assert node is not None
        return len(node.children) == 0

    def getUtility(self, node):
        assert node is not None
        return node.value
