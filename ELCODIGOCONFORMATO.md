Profe, mando el codigo por acá también porque el codigo que mandé se subió sin formatos de tilde y puntuación. Acá está llegar y ejecutar en pseint



Algoritmo CompraUtilesEscolares
	
	Definir i, cantidades, precios Como Entero
	Definir cupon, iva, descuento, peso, totalCompra Como Real
	Definir productos Como Cadena
	
		//constantes y variables 
		Dimensión productos[3]
		Dimensión precios[3]
		Dimensión cantidades[3]
		
		descuentoCantidad <- 0.05
		
		cupon <- 0.10
		
		Iva <- 0.19
	
		costoFijoEnvio <- 10
		
		EnvioporPeso <- 100
		
	
		//lista de productos y precios
		productos[1] <- "Lápices"
		productos[2] <- "Cuadernos"
		productos[3] <- "Destacadores"
		
		precios[1] <- 500 //Precio lápiz
		precios[2] <- 1000 //Precio cuaderno
		precios[3] <- 300 //Precio destacador
		
		Escribir "¡Bienvenida/o a la tienda de lápices, cuadernos y destacadores!"
		Escribir "---------------------------------------------------------------"
		Escribir "---------------------------------------------------------------"
		
		
		
		//solicitar la cantidad de cada producto
		Para i <- 1 hasta 3 Hacer
			
			Escribir "¿Cuántos ", productos[i], " deseas comprar? Ingresar solo números, por favor."
			Leer cantidades[i]
		FinPara
		
		
		
		
		totalCompra <- 0
		
		
		
		
		
		Escribir "---------------Detalle----------------" 
		
		
		//calcular y mostrar el valor por producto con descuento 0,05
		Para i <- 1 hasta 3 Hacer
			Si cantidades[i] >= 2 Entonces
				descuentoCantidad <- precios[i] * 0.05 * (cantidades[i] - 1)
			SiNo
				descuentoCantidad <- 0
			FinSi
			
		//valor total con el descuento del  0,05
			valorTotal <-  (precios[i] * cantidades[i]) - descuentoCantidad 
			
			
			
			
		//sumar el valor total de las 3 compras
			totalCompra <- totalCompra + valorTotal
			
			
		Escribir "Producto: ", productos[i]
		Escribir "Cantidad: ", cantidades[i]
		Escribir "Precio por unidad: $", precios[i]
		Escribir "Descuento aplicado (sobre 2 unidades): $", descuentoCantidad
		Escribir "Precio a pagar por ", cantidades[i], " ", productos[i], ": $", valorTotal
		Escribir "--------------------------------------"
			
			
		FinPara
		
		
		Escribir "--------------------------------------"
		Escribir "--------------------------------------"
		
		
		
		Escribir "Valor general de la compra es: $", totalCompra
		
		Escribir "--------------------------------------"
		Escribir "--------------------------------------"
		Escribir "--------------------------------------"
		
		
		
		
		//preguntar si tiene cupón
		Escribir "¿Tiene el cupón de 10% de descuento? Responder con sí o no" 
		Leer  descuentocupon
		
		
		//Convertir a minúsculas para evitar diferencias en "si" y "SI"
		descuentocupon <- Minusculas(descuentocupon)
		
		
		//aplicar el descuento con la respuesta válida y redondear el resultado con trunc
		Si descuentocupon = "si" O descuentocupon = "sí" Entonces
		
			totalCompra <- Trunc(totalCompra - (totalCompra * cupon))
			
			//mostrar el descuento luego de aplicar el cupon
		Escribir "---¡Felicidades, se aplicó el cupón!---"
		Escribir "El total general de la compra con el cupón de descuento es: $", totalCompra
			
		FinSi
		
		
		
		
		
		//calcular el IVA sobre el total después de aplicar los descuentos
		ivaCalculado <- Trunc(totalCompra * Iva)
		
		//sumar el IVA al total de la compra
		totalConIva <- Trunc(totalCompra + ivaCalculado)
		
		//resultados
		Escribir "--------------------------------------"
		Escribir "Tu compra está sujeta al impuesto de IVA"
		Escribir "IVA aplicado en esta compra: $", ivaCalculado
		Escribir "El nuevo valor total de la compra es: $", totalConIva
		Escribir "--------------------------------------"
		
		
		//agregar el costo de envio
		
		
		Escribir "Para realizar el envío hacia Viña del Mar, necesitamos el peso del envío en Kg"
		Escribir "Ingrese en números el peso del envío a realizar"
		Leer peso
		
		CostoEnvio <- costoFijoEnvio + (EnvioporPeso * peso)
		Escribir "El costo de envío es: $", CostoEnvio
		Escribir "--------------------------------------"
		Escribir "--------------------------------------"
		
		TotalFinal <- totalConIva + CostoEnvio
		
		Escribir "El total final a pagar es $", TotalFinal
		Escribir "¡Gracias por su compra!" 
