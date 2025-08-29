
using System.Net;
using System.Net.Mail;

namespace ConsoleApp1;

internal class EmailSender
{
    public void SendEmail(string to, string subject, string body)
    {
        SmtpClient smtpClient = new SmtpClient("smtp.gmail.com", 587);
        smtpClient.EnableSsl = true;
        smtpClient.UseDefaultCredentials = false;

        smtpClient.Credentials = new NetworkCredential("saqartvelostavdacvisdzalebi@gmail.com", "yvxm aaim fkot hmbr");


        MailMessage message = new MailMessage();
        message.To.Add(to);
        message.From = new MailAddress("saqartvelostavdacvisdzalebi@gmail.com");
        message.Subject = subject;
        message.Body = body;
        message.IsBodyHtml = true;


        smtpClient.Send(message);
    }
}
