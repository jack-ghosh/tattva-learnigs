Enums = Objects with values + types (real JavaScript, exists at runtime)
Utility Types = Tools to shape/customize types (Pick, Omit, Partial, etc.)

code snipets 
enum QuestionStatus {
    PENDING = "PENDING",
    VETTED = "VETTED",
    ACTIVE = "ACTIVE",
}

function getQuestionStatus(status: QuestionStatus) {
    return console.log(status);
}

getQuestionStatus(QuestionStatus.PENDING);

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

type QuestionForUser = Omit<Question, "id" | "status">;
type AnswerForUser = Pick<QuestionForUser, "correct_ans">;



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
type CreateQuestionDto = Omit<Question, "id" | "status">;

function getQuestion(question: CreateQuestionDto): AnswerForUser {
    console.log(question)
    return { correct_ans: question.correct_ans };
}

const newQuestion: CreateQuestionDto = {
    subject: "MATH",
    topic: "Algebra",
    body: "What is 2+2?",
    options: { a: "3", b: "4", c: "5", d: "6" },
    correct_ans: "4",
    difficulty: "EASY"
};

const ans = getQuestion(newQuestion)
console.log(ans)
