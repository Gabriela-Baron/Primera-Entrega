# Primera-Entrega Programacion 
ingreso de los datos (productos vendidos por vendedor, vendedores y productos).

# Primera-Entrega
ingreso de los datos (productos vendidos por vendedor, vendedores y productos).

# Para empezar organizamos los datos de los vendedores en  los que se especificaron los nombres, apellidos, tipo de documento y el numero correspondiente de cada uno de los vendedores.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/88d4d90c-c0e7-4a04-9fe0-6b7f498573d6)

# Siguiente a eso validamos los datos del producto en los que se determinaron los idsPriductos, la cantidad de los mismos, los precios y nombres de los productos correspondientes.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/e231190a-b206-4327-a179-58a39e470b48)

# Por medio del arreglo para almacenar las ventas totales por vendedor.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/2a6e03f1-5188-4fe2-a129-337f100c1270)

# Se generaron los datos en el formato CSV.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/d6733352-bbea-4914-b516-52349a742ac1)

# Se calcularon las ventas totales por vendedor, donde se tubo en cuenta los nombres de los vendedores, sus ventas totales, la cantidad de productos y se tuvieron en cuenta los precios de los productos.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/e6c80cbd-bd48-4905-8f27-b000d45d4c2f)

# Se relacionan las ventas totales por vendedor.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/c401deae-c55d-4e0d-8888-7c9d9419ebab)

# Se busca al vendedor que recaudo mas dinero, teniendo en cuenta la función if con el cual se tienen en cuenta las ventas totales por vendedor.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/1751b980-1a15-4f61-89eb-d36edba5c210)

# Finalizando se ejecuta el resultado del vendedor que recaudo mas dinero, con todas las especificaciones.

![image](https://github.com/Gabriela-Baron/Primera-Entrega/assets/164106618/582b8a86-a701-4444-b894-f8047007599f)

//

/*
 * INSTITUCION UNIVERSITARIA POLITECNICO GRAMCOLOMBIANO
 * MODULO CONCEPTOS FUNDAMENTALES DE PPROGRAMACION [GRUPO B02]
 * ENTREGA PROYECTO 1 - ESCENARIO 3
 * 
 * INTEGRANTES SUBGRUPO 10
 * ROBINSON AMADO PEÑA - 100273913
 * GABRIELA ALEXANDRA BARÓN BARRETO - 100285411
 * JEFERSON MEDINA GOMEZ - 100289745
 * KAROL MELISSA GOMEZ COLMENARES - 
 * DAVID SANCHEZ - 
 */

public class GenerateInfoFiles {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		//DATOS VENDEDORES
		String [] nombresVendedores = {"CARLOS ANTONIO", "VERONICA LISNEY","ANDRES"};
		String [] apellidosVendedores = {"CASTRO BERNAL", "CARO BUENO", "SOTO RODRIGUEZ"};
		String [] tipoDocumentos  = {"CC", "CC", "CC"};
		String[] numeroDocumentos = {"1070959820", "1010152330", "1012356427"};
		
		//DATOS DEL PRODUCTO		
		int [] idsProductos = {101,102,103};
		int [][] cantidadesProductos = {
				{12,24,32},
				{2,15,10},
				{20,10,4}
		};
		double [] preciosProductos = {12000000, 67000000, 89000000};
		String [] nombresProductos = {"VEHICULO", "CAMIONETA", "CAMION"};
		
		//ARREGLO PARA ALMACENAR LAS VENTAS TOTALES POR VENDEDOR
		double [] ventasTotalesPorVendedor = new double[nombresVendedores.length];
		
		
		
		//GENERAR DATOS EN FORMATO CSV
		System.out.println("Datos en formato CSV;");
		
		//CALCULAR VENTAS TOTALES POR VENDEDOR
		for (int i = 0; i < nombresVendedores.length; i++) {
			for (int j = 0; j < nombresProductos.length; j++) {
				ventasTotalesPorVendedor[i] += cantidadesProductos[i][j] * preciosProductos[j];
			}
			// Mostrar las ventas totales por vendedor
			System.out.println(nombresVendedores[i] + ";" + apellidosVendedores[i] + ";" + ventasTotalesPorVendedor[i]);
		}
		
        // Encontrar el vendedor que recaudó más dinero
        int indiceVendedorMasVentas = 0;
        double maxVentas = ventasTotalesPorVendedor[0];
        for (int i = 1; i < ventasTotalesPorVendedor.length; i++) {
            if (ventasTotalesPorVendedor[i] > maxVentas) {
                 maxVentas = ventasTotalesPorVendedor[i];
                 indiceVendedorMasVentas = i;
                
			}
			
		}
        // Mostrar el vendedor que recaudó más dinero
        System.out.println("El vendedor que recaudó más dinero es:");
        System.out.println("Nombre: " + nombresVendedores[indiceVendedorMasVentas]);
        System.out.println("Apellido: " + apellidosVendedores[indiceVendedorMasVentas]);
        System.out.println("Tipo de Documento: " + tipoDocumentos[indiceVendedorMasVentas]);
        System.out.println("Número de Documento: " + numeroDocumentos[indiceVendedorMasVentas]);
        System.out.println("Total Recaudado: " + ventasTotalesPorVendedor[indiceVendedorMasVentas]);
		
	}
}
