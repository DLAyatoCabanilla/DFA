
# Laboratory Activity 3

# DFA (Deterministic Finite Automata)

·         DFA refers to deterministic finite automata. Deterministic refers to the uniqueness of the computation. The finite automata are called deterministic finite automata if the machine is read an input string one symbol at a time.

·         In DFA, there is only one path for specific input from the current state to the next state.

·         DFA does not accept the null move, i.e., the DFA cannot change state without any input character.

·         DFA can contain multiple final states. It is used in Lexical Analysis in Compiler.

Example

Q = {q0, q1}

∑ = {a, b}

Below is an automaton that accepts a string that starts with a or b, any combination of a and b in the middle and ends with a.

 



                                                                             

 

Some Accepted Strings

Rejected Strings

ababaaba

ababb

bbba

baabab

ababa

ab

 

 

 

 

 

Java Equivalent:

class  Main {
    public static void main(String[] args) {
        String state = "q0";
        String input = "abbbabab";
        for(int x = 0; x < input.length(); x++){
            if(state.equals("q0") && input.charAt(x) == 'a'  ){

                state = "q1";
            }else if(state.equals("q0") && input.charAt(x) == 'b'  ){

                state = "q0";
            }else if(state.equals("q1") && input.charAt(x) == 'a'  ){

                state = "q1";
            }else if(state.equals("q1") && input.charAt(x) == 'b'  ){

                state = "q0";
            }else{
                System.out.println("Invalid input.. Exiting automaton");
            }

        }
        //check if state is final state
        if(state.equals("q1")){
            System.out.println("String accepted");
        }else{
            System.out.println("String not accepted");
        }
    }
}

 

Observe, study, and analyze the DFA and its equivalent Java code.

Below is another DFA. Study its flow, then create an equivalent JAVA program

DFA Details

Below is a DFA accepting strings ending with ‘01’ over input alphabets ∑ = {0, 1}



 

Use this templatefor your solution
