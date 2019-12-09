Web-Quiz

See `index.html` for demo and suggested HTML structure (the element class names are the important part).

#### Text Options

**`preventUnansweredText`** (String) *Defaut: 'You must select at least one answer.';* - the text to display if a user submits a blank answer while <code>preventUnanswered</code> is enabled

**`nameTemplateText`** (String) *Defaut:  '&lt;span&gt;Quiz: &lt;/span&gt;%name';* - the format of the quiz name; <code>%name</code> is a placeholder that will output the quiz name. Note: the "Quiz" span in the default value is used to enhance accessibility, it will not display on the screen.


#### Functionality Options

**`preventUnanswered`** (Boolean) *Default: false;* - prevents submitting a question with zero answers


**`scoreAsPercentage`** (Boolean) *Default: false;* - Returns the score as a percentage rather than the number of correct responses. If enabled, you'll also want to adjust <code>scoreTemplateText</code> to something like *'%score'*

## Base HTML Structure

            
            <label class="option"><input type="radio" name="option" value="1" /> <span id="opt1"></span></label>
            <label class="option"><input type="radio" name="option" value="2" /> <span id="opt2"></span></label>
            <label class="option"><input type="radio" name="option" value="3" /> <span id="opt3"></span></label>
            <label class="option"><input type="radio" name="option" value="4" /> <span id="opt4"></span></label>
            <button id="nextButton" class="next-btn" 

## Base Config Options

	See `quiz.js`

  	var currentQuestion = 0;
	var score = 0;
	var totQuestions = questions.length;

	var container = document.getElementById('quizContainer');
	var questionEl = document.getElementById('question');
	var opt1 = document.getElementById('opt1');
	var opt2 = document.getElementById('opt2');
	var opt3 = document.getElementById('opt3');
	var opt4 = document.getElementById('opt4');
	var nextButton = document.getElementById('nextButton');
	var resultCont = document.getElementById('result');

	function loadNextQuestion () {
    var selectOption = document.querySelector('input[type=radio]:checked');
    if(!selectOption){
        alert('Select an answer!');
        return;
    }
    var answer = selectOption.value;
    if(questions[currentQuestion].answer == answer){
        score += 10;


