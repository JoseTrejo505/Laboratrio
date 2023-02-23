using System;

class Program
{
    static void Main(string[] args)
    {
        
        Libro libro1 = new Libro(
            "Platero y yo",
            "Juan Ramón Jiménez​ ",
            "La obra Platero y yo trata sobre la vida de un burro muy querido llamado Platero.",
            25.99m,
            10,
            "Narrativo"
        );

        
        libro1.MostrarInformacion();

       
        libro1.AgregarInventario(5);

        
        Console.WriteLine($"Nueva cantidad en inventario: {libro1.CantidadEnInventario}");

       
        libro1.QuitarInventario(3);

      
        Console.WriteLine($"Nueva cantidad en inventario: {libro1.CantidadEnInventario}");
    }
}

public class Libro
{
    
    public string Titulo { get; set; }
    public string Autor { get; set; }
    public string Descripcion { get; set; }
    public decimal Precio { get; set; }
    public int CantidadEnInventario { get; set; }
    public string Categoria { get; set; }

    
    public Libro(string titulo, string autor, string descripcion, decimal precio, int cantidadEnInventario, string categoria)
    {
        Titulo = titulo;
        Autor = autor;
        Descripcion = descripcion;
        Precio = precio;
        CantidadEnInventario = cantidadEnInventario;
        Categoria = categoria;
    }

   
    public void MostrarInformacion()
    {
        Console.WriteLine($"Título: {Titulo}");
        Console.WriteLine($"Autor: {Autor}");
        Console.WriteLine($"Descripción: {Descripcion}");
        Console.WriteLine($"Precio: {Precio:C}");
        Console.WriteLine($"Cantidad en Inventario: {CantidadEnInventario}");
        Console.WriteLine($"Categoría: {Categoria}");
    }

    public void AgregarInventario(int cantidad)
    {
        CantidadEnInventario += cantidad;
    }

    public void QuitarInventario(int cantidad)
    {
        CantidadEnInventario -= cantidad;
    }
}
