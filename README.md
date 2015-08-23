# Hoja-de-Trabajo-2git
/*
 Michelle Bartra 14384
 UVG Algoritmos y Estructura de Datos
 Ejercicio 2: Calculadora
 Clase Calculadora
 */
public class Calculadora {
    //parametros
    private String ingreso;
    //inicializamos pila
    Pila pila = new Pila();
    //Getters y setter de ingreso
    public String getIngreso() {
        return ingreso;
    }
    
    public void setIngreso(String esto) {
        ingreso = esto;
    }
    // vemos si el caracter de la cadena es un numero o un string
    private static boolean PruebaisNumber(char caracter){
        try{
            Integer.parseInt(String.valueOf(caracter));
            return true; // si lo es no manda un true
        } catch (NumberFormatException e){
            return false;// si no lo es lo agarra el exception y nos manda false
        }
    }
    
    public void Operaciones(){
        //los operandos que se usaran para las sumas, resta, multiplicacion o division
        int primer = 0;
        int segundo= 0;
        
        for (int i=0; i< ingreso.length(); i++){ //se recorre la lista con un for, character por character
            
            char caracter = ingreso.charAt(i);// se guarda cada caracter en "caracter" para ser comparado despues
            if (PruebaisNumber(caracter)){ // si es un numero se guada en
                pila.push(ingreso.charAt(i));
            }
            else{       //si no es un numero es un operandor
                primer= Integer.parseInt((String.valueOf(pila.pop())));// convierte el primer valor de la pila en integer
                segundo= Integer.parseInt((String.valueOf(pila.pop())));//convierte el siguiente valor de la pila en int
                if (caracter ==('+')){ //si es una suma se suman los valares guardados en la pila
                    //se hace la suma
                    primer = primer + segundo;
                    pila.push(primer);}
                
                if (caracter ==('-')){
                    //restamos
                    primer = primer - segundo;
                    pila.push(primer);}
                
                if (caracter ==('*')){
                    //multiplicamos
                    primer = primer * segundo;
                    pila.push(primer);}
                
                if (caracter ==('/')){
                    //dividimos
                    primer = primer + segundo;
                    pila.push(primer);}
                if (caracter==(' ')){
                    int n=0;
                }}}}
    //imprimimos el resultado
    public void Resultado(){
        System.out.println("Resultado de toda la cadena: " + pila.pop());}
    
}
