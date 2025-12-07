# recursion
recursion
def generate_parenthesis(n):
    result = []

    def backtrack(current, open_count, close_count):
        # If the string is complete, add it
        if len(current) == 2 * n:
            result.append(current)
            return
        
        # If we can still add an opening parenthesis
        if open_count < n:
            backtrack(current + "(", open_count + 1, close_count)
        
        # If we can add a closing parenthesis
        if close_count < open_count:
            backtrack(current + ")", open_count, close_count + 1)
    
    backtrack("", 0, 0)
    return result


# Example
print(generate_parenthesis(3))
