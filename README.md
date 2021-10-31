# dta-base-management

int main()
{
     show();
     SDB obj ;
     long int type , test  , num_cases  ;
     long  int num_insert , num_del ,num_search ,check_insert , check_del ,check_search ;
     long double gpa;
     string name , id ;

     test = 1;

     cout &lt;&lt; "  Enter your choice: \n";
     num_cases = check_num(3);


     while(  test == 1 )
      {
       switch ( num_cases )
        {
        case 1 :
system("CLS");
                cout &lt;&lt; "You chose 1 to create a database, Please enter the Name, ID and GPA of the student\n";

                getline(cin ,name);
                while ( name&#91;0] &lt; 65 or name&#91;0] &gt; 122)
                 {
                  cout &lt;&lt; "  Wrong input !\n";
                  getline(cin ,name);
                 }

                 getline(cin ,id);

                 while ( !(cin &gt;&gt; gpa) or gpa &gt; 4)
                 {
                  cin.clear();
                  while ( cin.get() != '\n') continue;
                  cout &lt;&lt; " Wrong input !\n";
                 }
                 while ( cin.get() != '\n') continue;

                cout &lt;&lt; "  What type of database arrangement you want ? \n "
                     &lt;&lt;   " 1-Name     2-ID \n";
                type = check_num(2);

                obj.Construct(type , name , id , gpa);

                num_cases = menu();

                break ;

        case 2 :
system("CLS");
               cout &lt;&lt; "  You chose 2 to insert data , Please enter number of students you want to save . \n" ;

               check_insert = 1 ;
               num_insert = check_num(0) ;

               for ( int j = 1 ; j &lt;= num_insert ; j++)
               {
                   if ( check_insert == 1)
                   {
                   cout &lt;&lt; " Please enter name of student , Please enter the Name, ID and GPA of the student\n";
                   getline(cin ,name);

                   while ( name&#91;0] &lt; 65 or name&#91;0] &gt; 122)
                   {
                   cout &lt;&lt; "  Wrong Name ! \n";
                   getline(cin ,name);
                   }

                   getline(cin ,id);

                   while ( !(cin &gt;&gt; gpa) or gpa &gt; 4)
                   {
                    cin.clear();
                    while ( cin.get() != '\n') continue;
                    cout &lt;&lt; " Wrong input !\n";
                   }
                   while ( cin.get() != '\n') continue;

                  check_insert = obj.insertelement(name , id , gpa);
                  }
               }
                    num_cases = menu();

                 break;

        case 3 :
system("CLS");
              cout &lt;&lt; "You chose 3 to delete data, Please enter number of students you want to delete  \n";

              check_del = 1 ;
              num_del = check_num(0);

               for ( int k = 1 ; k &lt;= num_del ; k++)
               {
                   if ( check_del != 0)
                   {

                   cout &lt;&lt; "Please enter ID of student \n";
                   getline(cin , id);
                   check_del = obj.deleteelement(id);
                   if ( check_del == 3) k-- ;
                   }
               }

                num_cases = menu();

                 break;

           case 4 :
system("CLS");
               cout &lt;&lt; "You chose 4 to search on data,Please enter number of students you want to search on \n";
               check_search = 1 ;
               num_search = check_num();

               for ( int l = 1 ; l &lt;= num_search ; l++)
               {
                   if ( check_search != 0 )
                   {
                   cout &lt;&lt; " Please enter ID of student \n";
                   getline(cin , id);
                   check_search = obj.searchelement(id);
                   if ( check_search == 3) l--;
                   }
               }

            num_cases = menu();
                 break;


           case 5 :
           	system("CLS");
               obj.print() ;
               num_cases = menu();
                break ;

           case 6 :
system("CLS");
                int save_cheak ;
                save_cheak =obj.savefile();
                num_cases = menu();

                break ;

           case 7 :

                obj.help();
                num_cases = menu();
                break ;

           case 8 :

                exit(EXIT_SUCCESS);
                    break ;

           default :

            cout &lt;&lt; "Wrong input ! \n";
            cout &lt;&lt; "Enter your choice: \n";
            num_cases = check_num(3);
            break ;
         }
  }


    return 0;
}
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
101
102
103
104
105
106
107
108
109
110
111
112
113
114
115
116
117
118
119
120
121
122
123
124
125
126
127
128
129
130
131
132
133
134
135
136
137
138
139
140
141
142
143
144
145
146
147
148
149
150
151
152
153
154
155
156
157
158
159
160
161
162
163
164
165
166
167
168
int main()
{
     show();
     SDB obj ;
     long int type , test  , num_cases  ;
     long  int num_insert , num_del ,num_search ,check_insert , check_del ,check_search ;
     long double gpa;
     string name , id ;
 
     test = 1;
 
     cout &lt;&lt; "  Enter your choice: \n";
     num_cases = check_num(3);
 
 
     while(  test == 1 )
      {
       switch ( num_cases )
        {
        case 1 :
system("CLS");
                cout &lt;&lt; "You chose 1 to create a database, Please enter the Name, ID and GPA of the student\n";
 
                getline(cin ,name);
                while ( name&#91;0] &lt; 65 or name&#91;0] &gt; 122)
                 {
                  cout &lt;&lt; "  Wrong input !\n";
                  getline(cin ,name);
                 }
 
                 getline(cin ,id);
 
                 while ( !(cin &gt;&gt; gpa) or gpa &gt; 4)
                 {
                  cin.clear();
                  while ( cin.get() != '\n') continue;
                  cout &lt;&lt; " Wrong input !\n";
                 }
                 while ( cin.get() != '\n') continue;
 
                cout &lt;&lt; "  What type of database arrangement you want ? \n "
                     &lt;&lt;   " 1-Name     2-ID \n";
                type = check_num(2);
 
                obj.Construct(type , name , id , gpa);
 
                num_cases = menu();
 
                break ;
 
        case 2 :
system("CLS");
               cout &lt;&lt; "  You chose 2 to insert data , Please enter number of students you want to save . \n" ;
 
               check_insert = 1 ;
               num_insert = check_num(0) ;
 
               for ( int j = 1 ; j &lt;= num_insert ; j++)
               {
                   if ( check_insert == 1)
                   {
                   cout &lt;&lt; " Please enter name of student , Please enter the Name, ID and GPA of the student\n";
                   getline(cin ,name);
 
                   while ( name&#91;0] &lt; 65 or name&#91;0] &gt; 122)
                   {
                   cout &lt;&lt; "  Wrong Name ! \n";
                   getline(cin ,name);
                   }
 
                   getline(cin ,id);
 
                   while ( !(cin &gt;&gt; gpa) or gpa &gt; 4)
                   {
                    cin.clear();
                    while ( cin.get() != '\n') continue;
                    cout &lt;&lt; " Wrong input !\n";
                   }
                   while ( cin.get() != '\n') continue;
 
                  check_insert = obj.insertelement(name , id , gpa);
                  }
               }
                    num_cases = menu();
 
                 break;
 
        case 3 :
system("CLS");
              cout &lt;&lt; "You chose 3 to delete data, Please enter number of students you want to delete  \n";
 
              check_del = 1 ;
              num_del = check_num(0);
 
               for ( int k = 1 ; k &lt;= num_del ; k++)
               {
                   if ( check_del != 0)
                   {
 
                   cout &lt;&lt; "Please enter ID of student \n";
                   getline(cin , id);
                   check_del = obj.deleteelement(id);
                   if ( check_del == 3) k-- ;
                   }
               }
 
                num_cases = menu();
 
                 break;
 
           case 4 :
system("CLS");
               cout &lt;&lt; "You chose 4 to search on data,Please enter number of students you want to search on \n";
               check_search = 1 ;
               num_search = check_num();
 
               for ( int l = 1 ; l &lt;= num_search ; l++)
               {
                   if ( check_search != 0 )
                   {
                   cout &lt;&lt; " Please enter ID of student \n";
                   getline(cin , id);
                   check_search = obj.searchelement(id);
                   if ( check_search == 3) l--;
                   }
               }
 
            num_cases = menu();
                 break;
 
 
           case 5 :
           system("CLS");
               obj.print() ;
               num_cases = menu();
                break ;
 
           case 6 :
system("CLS");
                int save_cheak ;
                save_cheak =obj.savefile();
                num_cases = menu();
 
                break ;
 
           case 7 :
 
                obj.help();
                num_cases = menu();
                break ;
 
           case 8 :
 
                exit(EXIT_SUCCESS);
                    break ;
 
           default :
 
            cout &lt;&lt; "Wrong input ! \n";
            cout &lt;&lt; "Enter your choice: \n";
            num_cases = check_num(3);
            break ;
         }
  }
 
 
    return 0;
}
