# Robina-kappa
#include "txlib.h"

void find_word ( char data [], char word [], int datalen, int wordlen);
int find_sum (char data[], int start, int Nletters);
bool comparision (char data [], char word [], int letter_to_start,int Nletters);


int main ()

    {           //  0         1         2         3         4         5
                //  012345678901234567890123456789012345678901234567890123456789
    char data [] = "lhloh,k meow jbkgki� myow omofo,euwp meow twophddfgilweg,op";
    char word [] = "meow";
    int datalen = strlen (data);
    int wordlen = strlen (word);
    find_word (data, word, datalen, wordlen);
    //int a = 'm'+'e'+'o'+'w';
    //printf ("%d", a);
    //printf ("%d",find_sum (word, 0, wordlen));

    }


void find_word ( char data [], char word [], int datalen, int wordlen)

    {

    int sum_word = find_sum (word, 0, wordlen);
    int sum_data = find_sum (data, 0, wordlen);
    for (int i = wordlen; i < datalen - wordlen; i++)

        {

        if (sum_word == sum_data)

            {

            int a = comparision (data, word, i - wordlen, wordlen);
            //printf("%d ---- %d\n",a, i);
            if (a == false)

                {
                //printf("%d ---- %d",a, i);
                printf ("%d - %d = meow\n", i - wordlen, i - 1);

                }

            }

        sum_data = sum_data + data [i] - data [i - wordlen];

        }

    }

int find_sum (char data[], int start, int Nletters)

    {

    int sum = 0;
    for (int i = start; i < start + Nletters; i++)

        {

        int k = data[i];
        sum = sum + k;

        }

    return sum;

    }

bool comparision (char data [], char word [], int letter_to_start,int Nletters)

    {

    int a = 1;
    for (int i = 0; i < Nletters - 1; i++)

        {
        if (word[i] != data [Nletters + i])

            {

            a = 0;

            }

        }

    return a;

    }
