in generics we can send any type , we are mentioning at send time , 
and it can help with return value arr or single item 

code snipets 
function getFirst <T>(arr:T[]):T | null{
    if(arr.length===0) return null;
     return arr[0];
}

const questionInput= {
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
// const firstItem = getFirst([3,4,5]);
const firstItem = getFirst([questionInput]);
console.log(firstItem);

interface Apiresponse<T>{
    success:boolean
    data:T
    error?:string
}

type DifficultyLevel = "EASY" | "MEDIUM" | "HARD";
type QuestionStatus = "PENDING" | "VETTED" | "ACTIVE";


interface Question {
    id: string,
    subject: string,
    topic: string,
    body: string,
    options: {
        a: string,
        b: string,
        c: string,
        d: string,
    },
    correct_ans: string,
    difficulty: DifficultyLevel,
    status: QuestionStatus,
}

const response: Apiresponse<Question[]> =  {
    success:true,
    data:[questionInput]
}

const errorResponse: Apiresponse<string> =  {
    success:true,
    data:"",
    error:"Error response"
}

