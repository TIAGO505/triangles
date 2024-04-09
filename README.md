# triangles
import javax.swing.JOptionPane;

/**
 *
 * @author funci
 */
public class Triangulos_coor {

    public static void main(String[] args) {
       

        // Pedir las coordenadas de los vértices
        JOptionPane.showMessageDialog(null, "Ingrese las coordenadas del segundo vértice (x1 y1):");
        double x1 = Double.parseDouble(JOptionPane.showInputDialog("Ingresa las coordenadas de x1"));
        double y1 = Double.parseDouble(JOptionPane.showInputDialog("Ingresa las coordenadas de y1"));

        JOptionPane.showMessageDialog(null, "Ingrese las coordenadas del segundo vértice (x2 y2):");
        double x2 = Double.parseDouble(JOptionPane.showInputDialog("Ingresa las coordenadas de x2"));
        double y2 = Double.parseDouble(JOptionPane.showInputDialog("Ingresa las coordenadas de y2"));

        JOptionPane.showMessageDialog(null, "Ingrese las coordenadas del segundo vértice (x3 y3):");
        double x3 = Double.parseDouble(JOptionPane.showInputDialog("Ingresa las coordenadas de x3"));
        double y3 = Double.parseDouble(JOptionPane.showInputDialog("Ingresa las coordenadas de y3"));

        // Calcular las longitudes de los lados
        //
        double lado1 = Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
        double lado2 = Math.sqrt(Math.pow(x3 - x2, 2) + Math.pow(y3 - y2, 2));
        double lado3 = Math.sqrt(Math.pow(x1 - x3, 2) + Math.pow(y1 - y3, 2));

        // Determinar el tipo de triángulo
        String tipTr;
        if (lado1 == lado2 && lado2 == lado3) {
            tipTr = "Equilátero";
        } else if (lado1 == lado2 || lado1 == lado3 || lado2 == lado3) {
            tipTr = "Isósceles";
        } else {
            tipTr = "Escaleno";
        }

        // Calcular el perímetro
        double per = lado1 + lado2 + lado3;

        // Calcular el área usando la fórmula de Herón
        double s = per / 2;
        double area = Math.sqrt(s * (s - lado1) * (s - lado2) * (s - lado3));

        // Calcular los ángulos
        double ang1 = Math.toDegrees(Math.acos((lado2 * lado2 + lado3 * lado3 - lado1 * lado1) / (2 * lado2 * lado3)));
        double ang2 = Math.toDegrees(Math.acos((lado1 * lado1 + lado3 * lado3 - lado2 * lado2) / (2 * lado1 * lado3)));
        double ang3 = Math.toDegrees(Math.acos((lado1 * lado1 + lado2 * lado2 - lado3 * lado3) / (2 * lado1 * lado2)));

      
        JOptionPane.showMessageDialog(null, "Tipo de triángulo: " + tipTr);
        JOptionPane.showMessageDialog(null, "Perímetro: " + per);
        JOptionPane.showMessageDialog(null, "Área: " + area);
        JOptionPane.showMessageDialog(null, "Ángulo 1: " + ang1);
        JOptionPane.showMessageDialog(null, "Ángulo 2: " + ang2);
        JOptionPane.showMessageDialog(null, "Ángulo 3: " + ang3);

    }
}
