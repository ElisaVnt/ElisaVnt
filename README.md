#include <cs50.h>
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main(int argc, string argv[])
{
    // check for argument number
    
    if (argc != 2)
    {
    printf("Error argument number\n ");
    return 1;
    }
    
    //check for number of charrs
    int lenght = strlen(argv[1]);
    if (lenght != 26)
    {
        printf("Error number of charrs\n ");
        return 1;
    }
    
     // check if all charrs are alphabethical
     for(int i = 0; i < strlen(argv[1]); i++)
     {
         if(!isalpha(argv[1][i]))
         {
             printf("All charrs must be alphabetical\n ");
             return 1;
         }
         // check for repeating charracters
         for (int j = i + 1; j < strlen(argv[1]); j++)
         {
             if((argv[1][i]) == (argv[1][j]))
             {
             printf("There must be no repeating charrs\n ");
             return 1;
             }
         }
     }
     //prompt the user for text
     string s = get_string ("Entre le texte ma petite sexy prof: ");
     
     //print ciphertext
     printf("Le texte crypté: ");
     
      // preserve case and substitute
      for (int i = 0; i < strlen(s); i++)
      {
          if (isupper (s[i]))
          {
              printf("%c", toupper(argv[1][s[i] - 65]));
          }
          else if (islower (s[i]))
          {
          printf("%c", tolower (argv[1][s[i] - 97]));
          }
          else
          {
              printf("%c", s[i]);
          }
          
      }
      
      printf("\n");
}
