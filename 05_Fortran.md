---
layout: page
title: Fortran
permalink: /fortran/
order: 2
---

HelloWorld.f90

```fortran
PROGRAM HELLOWORLD
IMPLICIT NONE
REAL::TX, TY, TZ
INTEGER, PARAMETER::N=100, M=1000
REAL::A=2.61828
REAL(KIND=8)::B=3.141592                  ! KIND
CHARACTER(LEN=8)::CH                      ! LEN
INTEGER,DIMENSION(-3:5,7)::IAA            ! ARRAY

TX = 1.0;  TY = 2.0;   TZ = TX*TY

PRINT*, &
  TX, TY, TZ
PRINT*, 'N =',N, 'M =', M
PRINT*, 'A =',A, 'B =', B
PRINT*, 'HELLO WORLD'

END PROGRAM HELLOWORLD
```

----

selectcase.f90

```fortran
PROGRAM SelectCase
IMPLICIT NONE
INTEGER::N, K
WRITE(*,*) 'ENTER THE VALUE N = '
READ*, N

SELECT CASE(N)
  CASE(:0)
     K = -N
  CASE(10:20)
    K=N+10
  CASE DEFAULT
    K=N
  CASE(1:5)
    K=N*10
END SELECT
WRITE(*,*) 'K = ',K
END PROGRAM SelectCase
```

----

type.f90

```fortran
PROGRAM TYPE

INTEGER :: NP
REAL(KIND=8) :: X8

!X8 = REAL(NP, KIND = 8)
X8 = REAL(NP, KIND(X8))

PRINT*, X8

END PROGRAM TYPE
```

----

interface.f90

```fortran
PROGRAM TEST
IMPLICIT NONE
INTEGER::I=3, J=25
REAL::X=3.0, Y=25.0
PRINT*, 'THE RATIO IS', RATIOO(I,J)
PRINT*, 'THE RATIO IS', RATIO(X,Y)

CONTAINS
  INTEGER FUNCTION RATIOO(I,J)
  INTEGER::I,J
  RATIOO=I/J
  END FUNCTION RATIOO

  REAL FUNCTION RATIO(X,Y)
  REAL::X,Y
  RATIO=X/Y
  END FUNCTION RATIO
END PROGRAM TEST
```
