class jugador:
    id = 0
    nombre = ''
    num_armas = 1
    arma_uso = 1
    num_disparos = 0
    municiones = 9
    
    max_armas = 5
    max_municion = 10 #Protegido
    
    def _init_(self, name):
        self.nombre = name
    def setArmas(self):
        if(self.num_armas<self.max_armas):
            print("Arma recogida..")
            self.num_armas = self.num_armas + 1
    # cantidad 3
    def recogerMuniciones(self, cant):
        if(self.municiones<self.max_municion):
            if(self.municiones + cant <= self.max_municion):
                self.municiones = self.municiones + cant
            else:
                self.municiones = self.max_municion                
            
    def cambiarArma(self, arma):
        if(self.num_armas>=arma):
            self.arma_uso = arma
    def disparar(self):
        if(self.municiones>0):
            self.num_disparos = self.num_disparos + 1
            self.municiones = self.municiones - 1

def mostrar():
    print("Nombre ", jug1.nombre)    
    print("Armas ", jug1.num_armas)    
    print("Max Armas ", jug1.max_armas)    
    print("Arma Uso ", jug1.arma_uso)    
    print("Municiones ", jug1.municiones)    
    print("Disparos ", jug1.num_disparos)    

jug1 = jugador('Pepe')
opc = 0
while(opc!=5):
    mostrar()
    print("1. Recoger Armas")
    print("2. Recargar Municiones")
    print("3. Cambiar Arma")
    print("4. Disparar")
    print("5. Salir")
    opc = int(input("Opcion: "))
    if(opc == 1):
        jug1.setArmas()
    elif (opc==2):
        cantidad = int(input("Cantidad de Municiones: "))
        jug1.recogerMuniciones(cantidad)        
    elif (opc==3):
        armaseleccionada = int(input("Que arma vas a escoger: "))
        jug1.cambiarArma(armaseleccionada)    
    elif (opc==4):
        jug1.disparar()
       # tarea
archivo de clase
