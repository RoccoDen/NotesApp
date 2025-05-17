Create a multiple choice exercise in {targetLanguage} for level {userLevel} about {topicDescription} with {difficulty} difficulty.

Requirements:
- Create {numQuestions} questions
- Each question should test the specified topic
- Include clear explanations for each answer
- Make it suitable for {userLevel} level
- Focus on practical usage

Provide:
1. A clear instruction in {sourceLanguage} explaining what the user needs to do for the entire exercise
2. For each question, provide the actual question/exercise content in the target language {targetLanguage} and three options including the correct answer

Format the response as a minified JSON object with this structure:
{
  "instruction": "Clear instruction in {sourceLanguage} about what to do for the entire exercise",
  "questions": [
    {
      "question": "The actual question/exercise in target language",
      "type": "multiple_choice",
      "options": ["option1", "option2", "option3"],
      "correctAnswer": "correct answer",
      "explanation": "explanation"
    }
    // ... more questions
  ]
}

IMPORTANT: The response must be minified JSON with no extra spaces or line breaks.

Please wrap your response in a code block using triple backticks (```) and specify 'json' as the language, like this:
```json
{"instruction":"...","questions":[{"question":"...","type":"multiple_choice","options":["...","...","..."],"correctAnswer":"...","explanation":"..."}]}
```

----------------------------------------
Create a free text exercise in {targetLanguage} for level {userLevel} about {topicDescription} with {difficulty} difficulty.

Requirements:
- Create {numQuestions} questions
- Each question should test the specified topic
- Include clear explanations for each answer
- Make it suitable for {userLevel} level
- Focus on practical usage

Provide:
1. A clear instruction in {sourceLanguage} explaining what the user needs to do for the entire exercise
2. For each question, provide a sentence with a missing word (use ___ to indicate the missing word and Each _ rapresent a char spot for the answer). 
3. For each question, provide the word in {sourceLanguage} that the student need to text in {targetLanguage}
4. The correct answer and explanation for each question

Format the response as a minified JSON object with this structure:
{
    "instruction": "Clear instruction in {sourceLanguage} about what to do for the entire exercise",
    "questions": [
        {
            "question": "Sentence with ___ for the missing word",
            "sourceAnswer": "the answer that the student need to translate"
            "type": "free_text",
            "correctAnswer": "correct answer",
            "explanation": "explanation"
        }
    ]
}

Example: "This is ___ book" (not "Write the missing word: This is ___ book")

IMPORTANT: The response must be minified JSON with no extra spaces or line breaks.

Please wrap your response in a code block using triple backticks (```) and specify 'json' as the language, like this:
```json
{"instruction":"...","questions":[{"question":"...","type":"free_text","correctAnswer":"...","explanation":"..."}]}

-------------------

Create a character selection exercise in {targetLanguage} for level {userLevel} about {topicDescription} with {difficulty} difficulty.

Requirements:
- Create {numQuestions} questions
- Each question should test the specified topic
- Include clear explanations for each answer
- Make it suitable for {userLevel} level
- Focus on practical usage

Provide:
1. A clear instruction in {sourceLanguage} explaining what the user needs to do for the entire exercise
2. For each question, provide the actual question/exercise content in the {targetLanguage}
3. All characters needed to form the word(s) for each question
4. Some extra characters that are not needed for each question
5. all the chars need to be returned into a random order

Format the response as a minified JSON object with this structure:
{
    "instruction": "Clear instruction in {targetLanguage} about what to do for the entire exercise",
    "questions": [
        {
            "question": "The actual question/exercise in target language",
            "type": "character_selection",
            "chars": ["char1", "char2", "char3", ...],  
            "correctAnswer": "correct answer",
            "explanation": "explanation"
        }
    ]
}

Examples:
- For the word "hello": chars: ["s", "h", "e", "a", "t","l", "l", "o"]
- For "good morning": chars: ["g", "o","a", "y", "s", "o", "d", " ","i", "n", "m", "o","s", "t", "u", "r", "n", "g"]

IMPORTANT:
1. Include spaces as separate characters when needed
2. The response must be minified JSON with no extra spaces or line breaks
3. For languages with complex characters (like Chinese), provide whole characters not components

Please wrap your response in a code block using triple backticks (```) and specify 'json' as the language, like this:
```json
{"instruction":"...","questions":[{"question":"...","type":"character_selection","availableCharacters":[...],"extraCharacters":[...],"correctAnswer":"...","explanation":"..."}]}