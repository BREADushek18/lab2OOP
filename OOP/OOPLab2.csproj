using System;
using System.Collections.Generic;
using System.Xml.Linq;

namespace ObjectOrientedProgramming
{
    // Базовый класс для электронных документов
    public class Document
    {
        public string Title { get; set; }
        public string Author { get; set; }
        public string[] Keywords { get; set; }
        public string Subject { get; set; }
        public string FilePath { get; set; }

        public virtual void FindTitle()
        {
            Console.WriteLine($"Title: {Title}");
        }

        public virtual void FindAuthor()
        {
            Console.WriteLine($"Author: {Author}");
        }

        public virtual void FindKeywords()
        {
            Console.WriteLine("Keywords:");
            foreach (string keyword in Keywords)
            {
                Console.WriteLine($"- {keyword}");
            }
        }

        public virtual void FindSubject()
        {
            Console.WriteLine($"Subject: {Subject}");
        }

        public virtual void FindFilePath()
        {
            Console.WriteLine($"File Path: {FilePath}");
        }
    }

    // А теперь идут классы для определенных типов документов
    public class WordDocument : Document
    {
        public override void FindTitle()
        {
            Console.WriteLine($"Название документа Word: {Title}");
        }
    }

    public class PdfDocument : Document
    {
        public override void FindAuthor()
        {
            Console.WriteLine($"Pdf Document Author: {Author}");
        }
    }

    public class ExcelDocument : Document
    {
        public override void FindKeywords()
        {
            Console.WriteLine("Excel Document Keywords:");
            foreach (string keyword in Keywords)
            {
                Console.WriteLine($"- {keyword.ToUpper()}");
            }
        }
    }

    public class TxtDocument : Document
    {
        // Для этого класса не нужно переопрделение 
    }

    public class HtmlDocument : Document
    {
        public override void FindSubject()
        {
            Console.WriteLine($"Html Document Subject: {Subject}");
        }
    }

    // Класс Singleton управляет экземплярами документов
    public sealed class DocumentManager
    {
        private static readonly DocumentManager instance = new DocumentManager();
        private List<Document> documents = new List<Document>();

        private DocumentManager()
        {
            // Создано для предотвращения создания экземляра 
        }

        public static DocumentManager Instance
        {
            get
            {
                return instance;
            }
        }

        public void AddDocument(Document document)
        {
            documents.Add(document);
        }

        public void DisplayDocumentInfo()
        {
            foreach (Document document in documents)
            {
                Console.WriteLine("._._._._._._._._._._._._._._._._.");
                document.FindTitle();
                document.FindAuthor();
                document.FindKeywords();
                document.FindSubject();
                document.FindFilePath();
                Console.WriteLine("._._._._._._._._._._._._._._._._.звезда в шоке");
            }
        }
    }

    internal class Program
    {
        static void Main(string[] args)
        {
            WordDocument doc1 = new WordDocument
            {
                Title = "Образец документа Word",
                Author = "Крошечка Хаврошечка",
                Keywords = new string[] { "добро", "зло", "сказки" },
                Subject = "Это образец документа Word.",
                FilePath = @"C:\Documents\sample.docx"
            };

            PdfDocument doc2 = new PdfDocument
            {
                Title = "Образец документа PDF",
                Author = "Жанна д'Арк",
                Keywords = new string[] { "французы", "ведьма", "костер" },
                Subject = "Это образец PDF документа.",
                FilePath = @"C:\Documents\sample.pdf"
            };

            ExcelDocument doc3 = new ExcelDocument
            {
                Title = "Образец Excel документа",
                Author = "Зарплаты в маке",
                Keywords = new string[] { "100 рублей", "1500руб/год", "карьерный рост" },
                Subject = "Это образец Excel документа.",
                FilePath = @"C:\Documents\sample"
            };

            TxtDocument doc4 = new TxtDocument
            {
                Title = "Образец Text документа",
                Author = "Заметки психбольного",
                Keywords = new string[] { "черточки", "голоса в голове", "белые стены" },
                Subject = "Это образец text документа.",
                FilePath = @"C:\Documents\sample.txt"
            };

            HtmlDocument doc5 = new HtmlDocument
            {
                Title = "Образец HTML документа",
                Author = "Продам гараж.ru",
                Keywords = new string[] { "красные двери", "джакузи", "просторно" },
                Subject = "Это образец HTML документа.",
                FilePath = @"C:\Documents\sample.html"
            };

            // Добавляем документ в менеджера мм
            DocumentManager manager = DocumentManager.Instance;
            manager.AddDocument(doc1);
            manager.AddDocument(doc2);
            manager.AddDocument(doc3);
            manager.AddDocument(doc4);
            manager.AddDocument(doc5);

            // Отображение информации о документе
            manager.DisplayDocumentInfo();

            Console.ReadKey();
        }
    }
}