# flowchart TD
    A{GIR?} -->|Yes| B[1. Approach distance - N]
    B --> C[2. 1st Putt Length]

    A -->|No| D{Chipped in?}
    D -->|Yes| E[No putt recorded]
    D -->|No, missed green| C

    C --> F[1st Putt Outcome:<br/>Made it / Short / Long High / Long Low]
    F --> G{Made it?}
    G -->|No| H[2nd Putt Length + Outcome]
    H --> I{Made it?}
    I -->|No| J[3rd+ putt: number only,<br/>no length/outcome detail]
    I -->|Yes| K[4. Putts - N]
    J --> K
    G -->|Yes| K
    E --> K

    K --> L[5. Score - N]
    L --> M[6. Review voice parsing<br/>confirmation chips]
    M --> N{Chips correct?}
    N -->|No| O[Re-record / tap-correct]
    O --> M
    N -->|Yes| P[7. Save hole data]
    P --> Q[8. Next hole]
    Q --> A
