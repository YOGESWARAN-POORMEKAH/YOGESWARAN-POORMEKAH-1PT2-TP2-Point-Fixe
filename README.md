# YOGESWARAN-POORMEKAH-1PT2-TP2-Point-Fixe

"""YOGESWARAN POORMEKAH 1PT2

LAHRECH Abdel Ghani
Aéro 1 — Analyse numérique (MA123, 2020-2021)
TP 2 — Méthode du point fixe"""

print('='*10,"QUESTION 1",'='*10)
import math

def g0(x):
    return (1+math.sin(x))/2

def PointFixe(g,x0,epsilon,Nitermax):
    n = 1
    xold = x0
    xnew = g(xold)
    erreur = xnew-xold
    while abs(erreur)>epsilon and n<Nitermax:      
        xnew = g(xold)
        n+= 1        # n=n+1
        erreur = xnew-xold
        xold = xnew
        print(xnew,n,(xnew-xold)) 
    return xnew

print(PointFixe(g0,0,1e-4,1e4))



###QUESTION 2###

"===fonction 1==="
def g1(x):
    return (9-3*x)**(1/4)

a=PointFixe(g1, (3/2), 1e-4,1e4)
print(a)
print('-'*10)

def g1prim(x):
    return -(9-3*x)**(1/4)
aprim=PointFixe(g1prim, (3/2), 1e-4,1e4)
print(aprim)
print('-'*10)

print(PointFixe(g1, (3/2), 1e-4,1e4))    

"===fonction 2==="
def h(x):
    return math.acos((x+2)/3)

"===fonction 3==="
def i(x):
    return math.log(7/x)

"===fonction 4==="
def j(x):
    return math.log(10+x)

"===fonction 5==="
def k(x):
    return math.atan((x+5)/2)


#PointFixe(g, 1.5, 1e-4,1e4) #Ne converge pas
print("\n")

PointFixe(g1prim, -1, 1e-4,1e4) #Converge
print("\n")


PointFixe(h, 0, 1e-4,1e4) #Converge
print("\n")


PointFixe(i, 1, 1e-4,1e4) #Converge
print("\n")

PointFixe(j, 0, 1e-4,1e4) #Converge
print("\n")


PointFixe(k, 0, 1e-4,1e4) #Converge
print("\n")


"===fonction 6==="
def g6(x):
    return(math.log(x**2+3,math.e))
print(PointFixe(g6,1,10**-10,1000))#sol 1.873 40

"===fonction 7==="   
def g7(x):
    return(7-4*math.log(x,math.e))/3
print(PointFixe(g7,1,10**-10,1000)) #sol 1.658 105

"===fonction 8==="
def g8_a(x):
    return((17+2*x**2-4*x)**(1/4))
print(PointFixe(g8_a,0,10**-10,1000))#sol a=2.03

def g8_b(x):
    return(-(17+2*x**2-4*x)**(1/4))
print(PointFixe(g8_b,0,10**-10,1000))#sol b=-2.50

"===fonction 9==="
def g9(x):
    return math.log(7+2*math.sin(x),math.e) #sol 2.15
print(PointFixe(g9,0,10**-10,1000))

"===fonction 10==="
def g10(x):
    return math.log(10/(math.log(x**2+4,math.e)),math.e)
print(PointFixe(g10,0,10**-10,1000)) #sol 1.65


    




    
    

        
