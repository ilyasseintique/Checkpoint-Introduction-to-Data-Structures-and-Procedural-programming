ALGORITHM sum_distinct_elements
VAR
    set1, set2 : ARRAY OF INTEGER
    i, j, n1, n2, sum : INTEGER
    found : BOOLEAN
BEGIN
    sum := 0
FOR i FROM 0 TO n1-1 DO
    found := FALSE
    FOR j FROM 0 TO n2-1 DO
            IF set1[i] = set2[j] THEN
                found := TRUE
                BREAK
            END IF
      END FOR
        IF found = FALSE THEN
            sum := sum + set1[i]
        END IF
    END FOR

FOR i FROM 0 TO n2-1 DO
      found := FALSE
        FOR j FROM 0 TO n1-1 DO
            IF set2[i] = set1[j] THEN
                found := TRUE
                BREAK
            END IF
        END FOR
        IF found = FALSE THEN
            sum := sum + set2[i]
        END IF
    END FOR
END


//the second task

PROCEDURE dot_product(v1 : ARRAY OF REAL, v2 : ARRAY OF REAL, n : INTEGER, VAR ps : REAL)
VAR
    i : INTEGER
BEGIN
    ps := 0
    FOR i FROM 0 TO n-1 DO
        ps := ps + (v1[i] * v2[i])
    END FOR
END PROCEDURE
ALGORITHM check_orthogonality_procedure
VAR
    v1, v2 : ARRAY OF REAL
    n, i, j, num_pairs : INTEGER
    ps : REAL
BEGIN
    READ num_pairs
    FOR i FROM 1 TO num_pairs DO
        READ n
        FOR j FROM 0 TO n-1 DO
            READ v1[j]
        END FOR
        FOR j FROM 0 TO n-1 DO
            READ v2[j]
        END FOR
        CALL dot_product(v1, v2, n, ps)
        IF ps = 0 THEN
            OUTPUT "Vectors are orthogonal"
        ELSE
            OUTPUT "Vectors are NOT orthogonal"
        END IF
    END FOR
END
