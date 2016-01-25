# tree_plusplus
An STL alike C++ template library for tree structures.
## why using tree plus plus???
* multiple implementation provide flexible choice over space and time overhaul
* iterater pair / (optional) range interface
* depth/breath first traversal interface
* header only, least dependecy

## class list
* forward_tree_node : left-child right-sibling storage, minimial storage cost
* tree_node : first/last child storage, best balanced between storage and time
* kd_tree_node : fixed storage cost, best in time, random access children range

## Interface
### property : parent()
### property : prev_sibling() / next_sibling()
### property : first_child() / last_child()
### range : children()
### range : descendants() / descendants_breadth_first()
### range : nodes() / nodes_breadth_first()
## Usage example:
```cplusplus
class ast_node : public stdx::tree_node<ast_node>
{
    public:
    void print(ostream& os)
    {
        for(auto child : children())
        {
            child->print(os);
        }   
    }
};
```