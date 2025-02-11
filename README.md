#include <iostream>
#include <string>
#include <stdio.h>
#include <stdlib.h>
#include <cgicc/CgiDefs.h>
#include <cgicc/Cgicc.h>
#include <cgicc/HTTPHTMLHeader.h>
#include <cgicc/HTMLClasses.h>
using namespace std;
using namespace cgicc;
void set_content_type(string content_type) {
  cout << "Content-type: " << content_type << "\r\n\r\n";
}
void set_page_title(string title) {
  cout << "<title>" << title << "</title>\n";
}
void h1_text(string text) {
  cout << text << "\n";
}
int main() {
  Cgicc cgi;
  string name;
  set_content_type("text/html");
  cout << "<!doctype html>\n";
  cout << "<html lang=\"en\">\n";
  cout << "<head>\n";
  set_page_title("cgicc Test");
  cout << "</head>\n";
  cout << "<body>\n";
  cout << "<p>";
  // Grab the "name" variable from the form
  name = cgi("name");
  // Check to make sure it isn’t empty.
  if (!name.empty()) {
    cout << "Name is " << name << "\n";
  } else {
    cout << "Name was not provided.";
  }
  cout << "</p>\n";
  cout << "</body>\n";![Screenshot_2025-01-29-10-39-04-27_9e2bd530339e0e48020bd5cbcfc4854b](https://github.com/user-attachments/assets/76c1d488-727d-424e-95fc-f8feab335e1b)

  cout << "</html>";
  return 0;
}
