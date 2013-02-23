graphmatch
==========

Optimal bipartite graph matching algorithm gem for Ruby. Documentation here: http://rubydoc.info/github/pH14/graphmatch/master/frames

Sample usage for max-flow matching:
    Matching ['a', 'b'] to [1, 2], restrict it so 'a' can only reach 2.
    All path lengths are uniform (= 0)
  
    left = ["a", "b"]
    right = [1, 2]
    edges = {"a" => {2 => 0},
             "b" => {1 => 0, 2 >= 0}}
    Graphmatch.match(left, right, edges)
    >> { 'a' => 2, 'b' => 1 }
   
Sample usage for min-cost max-flow matching:
    Matching ['a', 'b'] to ['y', 'z'] with edge weights. 'a' is matched to 'y',
    'b' is matched to 'z'
  
    left = ['a', 'b']
    right ['y', z']
    edges = {'a' => {'y' => 1, 'z' => 100},
             'b' => {'y' => 100, 'z' => 1}}
    Graphmatch.match(left, right, edges, search = :min_cost)
    >> { 'a' => 'y', 'b' => 'z' }
