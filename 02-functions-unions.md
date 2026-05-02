Day - 02

today lern about funtion little more not everything , there is generics literal call signature 
but learn specifically for tattva need 

todays code snipets

// calculate score 
interface Answer {
  correct: number;
  wrong: number;
}

function calculateScore(ans: Answer): number {
  const score = ans.correct - ans.wrong * 0.33;
  return score;
}

const score = calculateScore({ correct: 65, wrong: 5 });
console.log(score); // 63.35

// Question Status Update
type DifficultyLevel = "EASY" | "MEDIUM" | "HARD";
type QuestionStatus = "PENDING" | "VETTED" | "ACTIVE";

interface Question {  
  id: string;
  subject: string;
  topic: string;
  body: string;
  options: {
    a: string;
    b: string;
    c: string;
    d: string;
  };
  correct_ans: string;
  difficulty: DifficultyLevel;
  status: QuestionStatus;
}

function getQuestionStatus(question: Question, status: QuestionStatus): Question {
  question.status = status;
  return question;
}

const questionInput: Question = {  
  id: "123",
  subject: "HISTORY",
  topic: "Indian History",
  body: "Independence day celebrate in India.",
  options: {
    a: "24,jul",
    b: "26,sep",
    c: "15,aug",
    d: "14,dec",
  },
  correct_ans: "15,aug",
  difficulty: "EASY",
  status: "PENDING",
};

const updatedQuestion = getQuestionStatus(questionInput, "VETTED");
console.log(updatedQuestion.status); // "VETTED"
