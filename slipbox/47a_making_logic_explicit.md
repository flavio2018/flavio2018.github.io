# Making logic explicit
<p style= "text-align: right"><i>Created 14/08/2021</i></p>

[47_abstractions_programming](47_abstractions_programming.md)

Reading code should be like looking at a a schema describing how a machine works. Some parts should be hidden, of course, but their logic should be immediately clear to the reader of a code where they are used. The reader should need the least possible amount of knowledge about the rest of the codebase to understand a piece of code.

This makes me think about a principle that could be formulated about code design and refactoring: *logic should be explicit* in the form of the code. When we add some additional functionality to pre-existing code and it gets heavy and unreadable, maybe because it's being adapted to some new need, then instead of keeping some old way of doing stuff the mechanism should be refactored, thinking about the simplest possible way of doing that and, if it's necessary adding new logic (e.g. a function, a method or a new class entirely), that it is explicitly showed to the user.

```
if action_str is list:  
    agent_did_action = False  
 for action_str_i in action_str:  
        if(bool(agent.action[agent.all_actions_dict_inv[action_str_i]])):  
            agent_did_action = True
```

The second `if` statement in the above piece of code requires to know what are the objects `action` and `all_actions_dict`, that are both inside `agent`, and also casts the result to `bool`. The desired behaviour could probably be refactored into something clearer for the reader and user of the software.