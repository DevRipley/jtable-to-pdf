
# Exportar Datos de JTable a PDF

Este proyecto proporciona una clase para exportar los datos de una tabla (`JTable`) a un archivo PDF, utilizando la biblioteca iText para crear el PDF y `JFileChooser` para permitir al usuario seleccionar la ubicación y el nombre del archivo PDF.

## Requisitos

### Usando Maven

Si estás utilizando Maven como tu herramienta de construcción, puedes añadir iText a tu proyecto añadiendo la siguiente dependencia a tu archivo `pom.xml`:

```xml
<dependency>
    <groupId>com.itextpdf</groupId>
    <artifactId>itextpdf</artifactId>
    <version>5.5.13.2</version>
</dependency>
```

### Usando Java Directamente

Si prefieres usar Java directamente sin un gestor de dependencias, puedes descargar la biblioteca iText desde su [repositorio en GitHub](https://github.com/itext/itextpdf) o desde su [sitio web oficial](https://itextpdf.com/en/products/itext-7). Luego, incluye los archivos `.jar` en el classpath de tu proyecto.

## Uso

### 1. Configuración

Asegúrate de que tienes la clase que maneja la exportación en tu proyecto.

### 2. Llamada a la Clase

Para exportar los datos de una `JTable` a PDF, simplemente llama al método que implementa la funcionalidad de exportación. Aquí tienes un ejemplo:

```java
ExportarPDF pdfExporter;

try {
    pdfExporter = new ExportarPDF();
    pdfExporter.exportarPDF(table);  // 'table' es tu JTable con datos
} catch (Exception ex) {
    JOptionPane.showMessageDialog(null, "Error al guardar en PDF: " + ex, "Error", JOptionPane.ERROR_MESSAGE);
}
```

### 3. Descripción del Código

- **ExportarPDF Class**:
  - `exportarPDF(JTable t)`: Este método abre un `JFileChooser` para seleccionar la ubicación del archivo PDF. Luego crea un archivo PDF y escribe los datos de la tabla en él, incluyendo los encabezados de la tabla.

### 4. Consideraciones

- El archivo se guarda con la extensión `.pdf`.
- Si ya existe un archivo con el mismo nombre, se sobrescribirá.
- El código maneja datos de tipo `String` al exportar los datos de la tabla.

## Ejecución

1. **Ejecuta tu aplicación**: Asegúrate de que tu `JTable` está poblada con los datos que deseas exportar.
2. **Exporta la tabla**: Utiliza el código anterior para exportar los datos. Se abrirá una ventana de diálogo que te permitirá seleccionar dónde guardar el archivo PDF.
3. **Verifica el archivo**: El archivo PDF se generará en la ubicación seleccionada.

## Notificaciones de Error

En caso de un error al intentar guardar el archivo, se mostrará una notificación de error usando un `JOptionPane`.

## Licencia

Este proyecto es de uso libre y puede ser modificado según las necesidades del usuario.
