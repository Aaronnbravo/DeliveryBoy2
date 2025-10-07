 DeliveryGo

 📋 Descripción del Proyecto
 
 Es un sistema de e-commerce desarrollado en C# que implementa patrones de diseño para crear una arquitectura robusta y mantenible. El sistema incluye un carrito de compras con funcionalidad de deshacer/rehacer, cálculo de envíos con diferentes estrategias, sistema de pagos con adaptadores y decoradores, y un sistema de pedidos con notificaciones.

🎯 Funcionalidades Principales
🛒 Gestión de Carrito

✅ Agregar, modificar y eliminar items

✅ Deshacer/Rehacer operaciones (Undo/Redo)

✅ Cálculo automático de subtotal

✅ Persistencia del estado del carrito

🚚 Estrategias de Envío

.Moto: Costo fijo de $1,280

.Correo: Gratis para compras mayores a $50,000, sino $3,580

.Retiro en Tienda: Gratuito

💳 Sistema de Pagos

.Tarjeta de Crédito

.Transferencia Bancaria

.Mercado Pago (nativo)

.Mercado Pago (vía Adapter)

.Aplicación de IVA (21% configurable)

.Aplicación de cupones de descuento

📦 Gestión de Pedidos

.Construcción paso a paso con Builder

.Notificaciones en tiempo real con Observer

.Seguimiento de estados: Recibido → Preparando → Enviado → Entregado


🎮 Uso de la Aplicación

---------------Menú Principal---------------

1. Agregar ítem al carrito

2. Cambiar cantidad de ítem  

3. Quitar ítem del carrito

4. Ver resumen de compra

5. Deshacer (Undo)

6. Rehacer (Redo)

7. Elegir método de envío

8. Realizar pago

9. Confirmar pedido

10. Suscribir/Desuscribir Logística

0. Salir
------------------------------------------


🏗️Flujo de Trabajo Típico

1.Agregar productos al carrito (Opción 1)

2.Ver resumen de la compra (Opción 4)

3.Seleccionar método de envío (Opción 7)

4.Realizar pago con IVA/cupón (Opción 8)

5.Confirmar pedido y recibir notificaciones (Opción 9)



👥 Distribución de Tareas

Ignacio Gutierrez - Comandos y Fachada

✅ Implementación del patrón Command para el carrito

✅ Clase Carrito con operaciones básicas

✅ Commands: AgregarItemCommand, QuitarItemCommand, SetCantidadCommand

✅ EditorCarrito para manejar historial (Undo/Redo)

✅ CarritoPort como adaptador

✅ Integración en CheckoutFacade


Aaron Bravo - Estrategias y Configuración

✅ Implementación del patrón Strategy para envíos

✅ Estrategias: EnvioMoto, EnvioCorreo, RetiroEnTienda

✅ Patrón Singleton en ConfigManager

✅ Configuración de umbrales y IVA


Franco Chocou - Pagos, Pedidos y Observadores

✅ Patrón Factory para creación de pagos

✅ Patrón Adapter para integración con SDK externa

✅ Patrón Decorator para IVA y cupones

✅ Patrón Builder para construcción de pedidos

✅ Patrón Observer para notificaciones

✅ Observadores: ClienteObserver, LogisticaObserver, AuditoriaObserver


🧪 Testing y Validación

El sistema incluye validaciones robustas para:

. Entradas numéricas válidas

. SKU únicos para productos

. Cantidades positivas

. Porcentajes de cupón válidos (0-1)

. Direcciones no vacías para pedidos

. Estados de pedido consistentes


👨‍💻 Próximas Mejoras

-Persistencia en base de datos

-Interfaz gráfica (GUI)

-Sistema de usuarios y autenticación

-Integración con APIs reales de pago

-Sistema de inventario

-Reportes y analytics


--Integrantes--

Franco Chocou  @FrancoChocou

Ignacio Gutierrez @nachoogutierrez

AaronBravo @AaronnBravo


"UML"
https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&target=self&highlight=0000FF&edit=_blank&layers=1&nav=1&title=UML.png&dark=auto#R%3Cmxfile%3E%3Cdiagram%20name%3D%22Page-1%22%20id%3D%22-iLuczsFaypwNS_6mBul%22%3E7V3bcuOoFv0aV%2FU8pEtXJ3lMnHSfVCUznnbPzJl%2BSREJy0wkcCGUxP31g662QLKxI6ycYz1FbAGS2GtfWIAzsifR21cKlosH4sNwZBn%2B28i%2BGVmW6Vhj%2FieVrHLJuWvmgoAiv6i0FszQT1gIjUKaIB%2FGtYqMkJChZV3oEYyhx2oyQCl5rVebk7D%2B1CUIoCSYeSCUpX8hny1y6YV1vpb%2FB6JgUT7ZHF%2FmdyJQVi6%2BJF4An7xuiOzbkT2hhLD8KnqbwDAdvHJc8nZfWu5WL0YhZioNfv%2Fb%2Bnl2E3z%2F8ePHxfivp%2FFD8kzPil5eQJgUHzylJKAgKt6ZrcqBiF9RFALMS9dzgtmsuGPyMghRgPm1x98EUi54gZQhPoZXxQ1GllzqLVDo34MVSdL3jRnwnsvS9YJQ9JN3C8KiT36bsgIOtlGrMUtbcnEqpTDmdablIJiC6AG81Sreg5gVAo%2BEIVjG6Kn6jAjQAOFrwhiJikqvC8TgbAm8tM4rRziXFSPGPxG%2BtarCrBTMLQOSCDK64lWKBiUkCpu4LIqva4BZRiFbbICrEoIC1EHV81rv%2FKJQ%2FR4wsCQYnPHi3YRbEGJkSijjxUcvL45Sm7bNdHzSWpMF9J65Fr8AD%2FgwrTcvrmrVptBHPplB%2BoK8rNayLhDgxgeXZTCg5BlOSEg4rm4wyfGHwlAQlRAM4Zy1AjDmikQ4uM%2Fq3Dhryff0diZoUjjhvc3DzHQXyPchTuFEGGAgx46hCop2C5SRUkDDVoTGuS5k2BIyRhb%2FWuMBIPzplw0dF2LCNQboA8TJlCLsoSUIG6pdBRQGgN4xGLV38g3GSQSzpwzgaAKHaSiiw9TmOBwZHhNrdHWN0kgwT0eKF6%2BvN1RcdypDkNEXZC7qUcZRBctYF1jcFl%2By3Rv8niDWenMCoicE6ARghnzgN9T4ClnaNp5hrogFYQ1VZskT4ybb5Kj%2BwD5pEH%2BDufhU%2FZLTSdAybV1IG0tIO8DrGIPXOcDruHWv8wHcznljcjspk9m2vPbW5zK6UQ1mgtM1%2BnEnRu%2FqUvPFEF1OAmgXikC70AW0y7bgMgQWjYHFtT5aOltSlEJguUd8vKxxmKoo9Q38OmDZGBiPKPUVp2vYl51EEG1ZoymzobUQ8ilVZ1sI%2BcTVx4f3l5Q3y7UuhAHIqjiSVx1Zk%2FSNMEvbPBESbg0dhg89FIGGShuhx7j7BoH%2FGw5XHDMh9BgieIBbM9zGvZMnpky75tAZwsjRwkiVj%2FY3WTXbONbSTRiz50Qy%2B%2BrmryR6olC6X7kLY0r5JZEqcMeTpbi5TzpdL5Fb4fvJDH1u4hCSlUQRwLJWB4K1O1dyPj4wI9WHlDaG9fYNegmDW6agJ2v93VCZ2tbfTJnK3CA09jTzIWM4wMwvLutmbqoSEBozhgMpzTy7zKehJ2zy3RCZjjbttjGZgxc%2FUKXniirVRxXJnKGwvDA48KPlaXb%2F65PlJFRw4PlYl9xhFdzX%2FGHC7Vzw6TvbUOjL%2BDodz9AN56jN2VttnOO3BH8q1TmsHHWj7d7jgCUzfjun8rf4BZEZo4DBYKUaKIYJ%2Ffu35dqqcNE3obfaqMEJCL0kBHRCYka2Lg9IPOGp%2BgarG55P20zfkmm%2BzPQfyJAfajV7p2721QpBj2bfxuMNZr%2B%2F2X9wgs9q2KsonKgYbP94m6SVlwP15YjN5J7aYRwxWzQeYSoYzuKo%2BYoPvsXROmyPYxk1vu%2FcSzIF6TaX1v0oE4LniHLrzAGUVcwvB8x81N2KbtMUQlAW9ANYhhHuXhYkIBiEt2spH68E%2B9AvRmtd555kQ5867X8gY6siToCEeyYeKVhURpH8memDtntq%2Fl4koR7cNuIFmcrjUgC3sgF2s2ooDAFDL%2FU3aRr4rOkVpWC1UWFJ%2BGQ93uh5SvKtFAVwxrYQUkzhXO5%2B9flF%2FgZrCFSf8g5PIhPSO4mI3NJ%2Fe4p5mODJxcBE6EtLXBET%2Fc9JyjeSY4%2FHEq7gnzxw5Ag5Yf7R6oZt1jbZcJ0%2BfD98Q%2By%2FafPPblH6u%2Bgsvb552yysygLm35s3cs7Lctbss%2BHYpWDdNivVGk8hRXzUUn%2BzodWtEWirq9wZl0rt7oxLttGMEuW49D5DllccJiFKPfO%2Brn2YcXawAdVV%2FfUHfauRtrwqcbZJIT3iE%2BeQ7G5%2BpEGfAtuWCYbYrKxE1eMA%2BmKzbIV9BGuFMKk6UbMdxYDY5jKPFBDlhZeM6AgeAAbBEA6PujnH7f88hi2vvuThkGPRK1mwNTiMR4T5PextO4OR0bJfKe8hvoGxv63q3Z9XJ%2Byku1mt0cbA2vJqTa6%2FuwoDIj4GVb6LGNWnSnmdRY632L9Kf0SQl55CkrpaPrf0v6Cwmtri8jcLTaseR9eBuIMpsLs5AzZ3zH47jOBjxQDeouoN3Zpb2ar9GFmJQrWFVbxqJ0%2FZRf6hRastXKwjdGSKHeUjIXXUFS1ryws8HomWJEaNJ3k34OkjEBHsf18g%2FG6QmpsQrQC7C6R1ksb9eCBt4eaOBVIRW7ZI1aqCVGQQjg5See2gB5DWPal5kCc1jgdS5TUra2u6fGZ8tqS4qRW2Y%2FHA9KGwlTpShO26o7Iimc9jqAXa5VawISfYglBVf9t2tPJYyL0QppbSlh1V5EodiacBNDtcp%2BmMQDsqyRLW3atxCCgPyQHM0V45gA%2FiRfXgPhDac0Ygch9Wue9zX4Ce95wROCrUZdcA%2FR%2FzmsoJwAfzmrZ5ZK%2B5734byYrcI%2ByfcVR2VZ14olAeaNhN%2F7fkvMeCvNl2AmBfyEsdibmybj%2Fc8Esx%2Fw%2BJQpegVM0N%2BgaltDNd3CGqCkrxfIsjMqq6Qdl0mEUzKI%2FBYGnLXhUB2nOeIMJKCu%2FK%2BOyZc3WalnQ%2BUPJ6EM56pDnLnysr3Y1z4KRG7Mi8dJVwsW%2F%2B6ArPscfu9vcSfg%2Bo3BGiN98cFqt2bzdR9Zxtu3T7olQPzjeljjrLN3lx%2FZ%2FJ8urr%2F%2B9m3%2F4L%3C%2Fdiagram%3E%3C%2Fmxfile%3E
