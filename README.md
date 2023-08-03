# ejercicio-clases

class Humano:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def trabajar(self, lugar):
        print(f"{self.nombre} está trabajando en {lugar} .")

    def saludar(self, otra_persona):
        print(f"{self.nombre} saluda a {otra_persona}.")
    
    #def preguntar(self, edad):
    #print(f"{self.nombre} le pregunta)


persona1 = Humano(nombre="Emanuel", edad=20)
#persona2 = Humano(nombre="Emma", edad=15)

persona1.trabajar("SENATI")
persona1.saludar("Liam")
persona1.saludar("Alex")


#persona2.trabajar("INTERCORP")
#persona2.saludar("Gianne")
#persona2.saludar("Amer")

from datetime import datetime
class Persona:
    def __init__(self, nombre, genero, fecha_nacimiento):
        self.nombre = nombre
        self.genero = genero
        self.fecha_nacimiento = fecha_nacimiento

class Alumno(Persona):
    def __init__(self, nombre, genero, fecha_nacimiento):
        super().__init__(nombre, genero, fecha_nacimiento)
   
    def calcular_edad(self):
        fecha_actual = datetime.now()
        fecha_nacimiento = datetime.strptime(self.fecha_nacimiento, "%Y-%m-%d")
        edad = fecha_actual.year - fecha_nacimiento.year - ((fecha_actual.month, fecha_actual.day) < (fecha_nacimiento.month, fecha_nacimiento.day))
        return edad
   
# Crear una instancia de la clase Alumno
alumno1 = Alumno(nombre="Juan", genero="Masculino", fecha_nacimiento="2003-12-05")

# Calcular y mostrar la edad del alumno
edad_alumno1 = alumno1.calcular_edad()
print(f"Nombre: {alumno1.nombre}")
print(f"Edad: {edad_alumno1} años")
