Learning begains today - 01

types vs interfaces 

types : can not be reopend after declearation , good for unions and composistion  
type Point = { lat:number, lng:number}

interfaces : when you want to changes input mechanism or data structure then interface your partner 
interface Address { city : string }
interface Address { locality : string }

what i understand about type of typescript is that , type is one thing i face many time that it is array or is it object , a prime example is mogodb always gives you 
object data type for id but you use string as in front end this alone create dificulty for me 
refreshtoken some times comes in object sometime as string you have check separetly it is obj or str 

type RefreshToken = string | {token : string , expireAt: Date   eleiminates that issue 

my final snippets 

type DifficultyLevel = "EASY" | "MEDIUM" | "HARD";
type QuestionStatus = "PENDING" | "VETTED" | "ACTIVE";


interface Question {  
  id:string,
  subject: string,
  topic:string,
  body: string,
  options: {
    a:string,
    b:string,
    c:string,
    d:string,
  },
  correct_ans:string,
  difficulty: DifficultyLevel,
  status:QuestionStatus,
}

function generatedQuestion( questions : Question ):Question {
  console.log(questions)
  return questions; 
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
  correct_ans:"15,aug",
  difficulty: "EASY",
  status: "ACTIVE",
}

generatedQuestion(questionInput);


