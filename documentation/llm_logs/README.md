# Collection of input and outputs from Sidekick's chatbot feature.

**Note:**  

1. **Formatting of logs**:  
    ```
    Input:
    <user prompt>
    Decompiled Code (<IL level>):
    <decompiled code>
    Output:
    <chabot output>
    ```
2. **Formatting of decompiled code**:
    ```
    <memory address>|   <decompiled code>
    ```  
3. **Conversation continuation**:  
- All rounds of a conversation will be recorded as `Round <round number>`
- All conversation logs with the same number are continuations of the same instance conversation with the LLM. 
- For conversations with only `1 set of decompiled code`, the decompiled code will only be logged in `Round 1` of the conversation. (Will be tagged with: `same as above` for clarity)
- For conversations with `multiple sets decompiled code`, the decompiled code will be included in the Round where the new decompiled code is introduced into the conversation. (Will be tagged with: `new function introduced here` for clarity)