// Author: Muhammad Asad Naveed
// U.No.: 3035957848
// Assignment 2 Question 2
// Description: Write a C++ program that uses the Naked Single technique alone to solve a Sudoku game as much as possible as described above.

// use https://www.sudoku-solutions.com/ to generate a board
// this website also supports using particular techniques to solve for a board
// from preferences, choose Naked-Singles only or partial solving
// then click "Solve Partially", you may then cross-check with your progran output

#include <iostream>

using namespace std;

// IMPORTANT:  Do NOT change any of the function headers
//             It means that you will need to use the function headers as is
//             You may add other functions wherever appropriate

// get user input and store the game board in the 2D array b
void ReadBoard( int b[][9] )
{
  for(int x=0; x<9; x++)
  {
    for(int y=0; y<9; y++)
    {
      cin>>b[x][y];
    }
  }

}

int naked_single( int duplicate_array[] );

// display the game board stored in the 2D array b
void PrintBoard( int b[][9] )  
{
  for(int i=0; i<9; i++)            //loop to go through each and every element of the array
  {
    if(i==3 || i==6)
    {
      cout<<"------+-------+-------"<<endl;
    }
    for(int j=0; j<9; j++)
    {

      if (b[i][j] != 0)
      {
        cout<<b[i][j]<<" ";

      }
      else{
        cout<<"x ";
      }
      if(j==2 || j==5)
      {
        cout<<"| ";
      }

    }
    cout<<endl;
  }

}


bool check_board( int row, int col, int b[][9] )
{
  // An array, if a number is found in the row or coloumn or within the block it is makred as zero

  int duplicate_array[9] = { 1, 2, 3, 4, 5, 6, 7, 8, 9 };


  for ( int col = 0;  col < 9; col++ )
  {
    if ( b[row][col] != 0 )   
    {                       
      int num = b[row][col];

      for ( int k = 0;  k < 9; k++ )
      {
        if ( num == duplicate_array[k] )    
        {
          duplicate_array[k] = 0;
          break;
        }
      }
    }
  }

  // now moving through the columns and eleiminating the numbers from the check_array[] which are present on the board column 'c'

  for ( int row = 0; row < 9; row++ )
  {
    if ( b[row][col] != 0 )
    {
      int newnum = b[row][col];

      for ( int j = 0; j < 9; j++ )   // To go through the check_array and making the number to zero which is found so that we know that column 
      {                              // has that number
        if ( newnum == duplicate_array[j] )
        {
          duplicate_array[j] = 0;
          break;
        }
      }
    }
  } 
 
 
   if(row== 0 || row==3 || row==6 )          //the following if else statement are required to go through each bloack of the game to find all the numbers in them
   {
     if(col==0 || col==1 || col==2 )
     {
       for(int p=row; p<row+3; p++)
       {
         for(int u=0; u<3; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
     }
     else if(col==3 || col==4 || col==5 )
     {
       for(int p=row; p<row+3; p++)
       {
         for(int u=3; u<6; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
               }
             }
           }
           
         }
 
       }
     }
 
     else if(col==6 || col==7 || col==8)
     {
       for(int p=row; p<row+3; p++)
       {
         for(int u=6; u<9; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
               }
             }
           }
           
         }
 
       }
 
     } 
   }
   else if(row== 1 || row==4 || row==7 )
   {
     if(col==0 || col==1 || col==2 )
     {
       for(int p=row-1; p<row+2; p++)
       {
         for(int u=0; u<3; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
     }
     else if(col==3 || col==4 || col==5 )
     {
       for(int p=row-1; p<row+2; p++)
       {
         for(int u=3; u<6; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
     }
 
     else if(col==6 || col==7 || col==8)
     {
       for(int p=row-1; p<row+2; p++)
       {
         for(int u=6; u<9; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
 
     } 
   }
   else if(row== 2 || row==5 || row==8 )
   {
     if(col==0 || col==1 || col==2 )
     {
       for(int p=row-2; p<row+1; p++)
       {
         for(int u=0; u<3; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
     }
     else if(col==3 || col==4 || col==5 )
     {
       for(int p=row-2; p<row+1; p++)
       {
         for(int u=3; u<6; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
     }
 
     else if(col==6 || col==7 || col==8)
     {
       for(int p=row-2; p<row+1; p++)
       {
         for(int u=6; u<9; u++)
         {
           if(b[p][u] !=0)
           {
             for(int i=0; i<9; i++)
             {
               if(duplicate_array[i]==b[p][u])
               {
                 duplicate_array[i]=0;
                 break;
               }
             }
           }
           
         }
 
       }
 
     } 
   }
 
   int count = 0; 
   int num = 0;  // to store the possible number that can fill the empty cell
 
   for ( int i = 0; i < 9; i++ )  // loops through the check_array and increments count with each possible value of the empty cell
   {
     if ( duplicate_array[i] != 0 )
     {
       count++;
       num = duplicate_array[i];
     }
   }
   
   if ( count == 1 )  // if count is 1, it tells that it is a naked single and that possible value is returned which is used to fill the empty cell
   {
     b[row][col] = num;
     return true;
   }
   else
   {
       return false;
   }
    
   


}



// solve a game board stored in b using the Naked Single technique only
// the (partial) solution is stored in the input array b
void SolveBoard( int b[][9] )
{

  

  int count;
  bool flag = true;

  while ( flag != false )  //continue until naked single do not work
  { 
      count = 0;
 
 
     for ( int x = 0; x < 9; x++ )   // To loop through the rows
     {
       for ( int y = 0; y < 9; y++ )  // to loop through the columns
       {
         if ( b[x][y] == 0 ) 
 	    {
             if ( check_board( x, y, b ) )
 	        {
                 break;
 	        }
 	        else
 	        {
 	            count++;  // if no naked single is found count is incremented
 	        }
 	    }
 	    else
 	    {
 	        count++;
 	    }
       }
 
     }
 
    if ( count == 81 ) // if didn't found any naked single, loop is existed
     {
       flag = false;
     }
   }
 
 
}

// You do not need to change anything in the main() function
int main()
{
  int board[9][9];    // the 9x9 game board

  ReadBoard( board );   // to get input

  cout << "Input Sudoku board:" << endl;
  PrintBoard( board );   

  // solve the board using the naked single technique only
  SolveBoard( board );  

  cout << endl;
  cout << "Final Sudoku board:" << endl;
  PrintBoard( board );   // Displaying the board after solving

  return 0;
}
