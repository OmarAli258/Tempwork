CHIP A6Q2201854908 {
    IN a, b, c, d;
    OUT f;
    PARTS:
    
    // Intermediate signals for the terms
    NotA = NOT(a);
    NotB = NOT(b);
    NotC = NOT(c);
    NotD = NOT(d);
    
    // Term 1: ¬a ∧ ¬b ∧ (d ∨ c)
    Or1 = OR(c, d);
    Term1 = AND(NotA, NotB, Or1);
    
    // Term 2: ¬a ∧ b ∧ (¬c ∧ ¬d ∨ c ∧ ¬d)
    NotCAndNotD = AND(NotC, NotD);
    CAndNotD = AND(c, NotD);
    Or2 = OR(NotCAndNotD, CAndNotD);
    Term2 = AND(NotA, b, Or2);
    
    // Term 3: a ∧ ¬b ∧ ¬c ∧ ¬d
    Term3 = AND(a, NotB, NotC, NotD);
    
    // Final OR to combine all terms
    f = OR(Term1, Term2, Term3);
}
