%fatos
gerou(kelly,maria).
gerou(cleber,maria).
gerou(cleber,bruna).
gerou(maria,julia).
gerou(maria,pedro).
gerou(pedro,lucas).

feminino(kelly).
feminino(maria).
feminino(bruna).
feminino(julia).
masculino(cleber).
masculino(pedro).
masculino(lucas).
%regras
filho(X,Y) :-
    gerou(Y,X),masculino(X).
filha(X,Y) :-
    gerou(Y,X),feminino(X).

mae(X,Y) :-
    gerou(X,Y),feminino(X).
pai(X,Y) :-
    gerou(X,Y),masculino(X).

irmao(X,Y) :-
    gerou(Z,X),gerou(Z,Y),masculino(X).
irma(X,Y) :-
    gerou(Z,X),gerou(Z,Y),feminino(X).


avo(X,Z):-
    gerou(X,Y),gerou(Y,Z),masculino(X).
avof(X,Z):-
    gerou(X,Y),gerou(Y,Z),feminino(X).

bisavo(W,Z):-
    gerou(W,X),gerou(X,Y),gerou(Y,Z),masculino(W).
bisavof(W,Z):-
    gerou(W,X),gerou(X,Y),gerou(Y,Z),feminino(W).

