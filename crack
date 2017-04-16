#define _XOPEN_SOURCE
#include<cs50.h>
#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>
#include<string.h>
#include<unistd.h>

char * strncpy(char * dest, const char * src, size_t n);

int main(int argc, string argv[])
{
    if (argc != 2)
    {
        printf("Usage: ./crack hash\n");
        return 1;
    }
    
    else
    {
        // saves the first two characters from input argv[1] in a variabel called salt
        // next five lines is based on code from https://www.tutorialspoint.com/c_standard_library/c_function_strncpy.htm
        char hash[20];
        char salt[5];
        memset(salt, '\0', sizeof(salt));
        strcpy(hash, argv[1]);
        strncpy(salt, hash, 2);
    
        
        printf("Salt: %s\n", salt);
        
        
        /* moves the characters in the hash two times to the left. Thereby removing the salt
        for (int h = 0; h < 2; h++)
        {
            for (int j = 0, n = strlen(hash); j < n; j++)
            {
                hash[j] = hash[j+1];
            } 
            printf("%s\n",hash);
        }
        */

        bool searching = true;
        char word[4];
        string key;
        string test;
        string s;
        do
        {
            for (int i=0; i<='z'; i++)
            {
                for (int ii=0; ii<='z'; ii++)
                {
                    for (int iii=0; iii<='z'; iii++)
                    {
                        for (int iv=0; iv<='z'; iv++)
                        {
                            word[0] = i;
                            word[1] = ii;
                            word[2] = iii;
                            word[3] = iv;
                            test = word;
                            
                            printf("Checking: %s\n", test);
                            
                            s = crypt(test, salt);
                            
                            if (0 == (strcmp(s, hash)))
                            {
                                key = test;
                                searching = false;
                            }
                            
                            if (iv==0)
                            {
                                iv = 'A'-1;
                            }
                        
                            if (iv=='Z')
                            {
                                iv = 'a'-1;
                            }
                        }
                    
                        if (iii==0)
                        {
                            iii = 'A'-1;
                        }
                    
                        if (iii=='Z')
                        {
                            iii = 'a'-1;
                        }
                    }
                    
                    if (ii=='Z')
                    {
                        ii = 'a'-1;
                    }
                    if (ii==0)
                    {
                        ii = 'A'-1;
                    }
                }
                
                if (i=='Z')
                {
                    i = 'a'-1;
                }
                if (i==0)
                {
                    i = 'A'-1;
                }
            
                if (i=='Z')
                {
                    i = 'a'-1;
                }
            }
            searching = false;
            return 1;
        }
        while(searching);
        
        if (key != NULL)
        {
            printf("%s\n", key);
        }
        
        else
        {
            printf("Did not find key\n");
        }

        
    }
}
