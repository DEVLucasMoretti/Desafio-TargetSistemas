(1) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores 
(exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...),escreva um programa na linguagem que desejar onde, informado um número,ele 
calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.


Console.Write("\n(1) Informe um número para verificar se pertence a sequência de Fibonacci: ");
string choose = Console.ReadLine()!;

try
{
  //Chamada da função, passando o parâmetro que é o input do usuário
  FibonacciFind(choose);  
}
catch(Exception e) 
{
    Console.WriteLine($"Erro: {e.Message}\nPor favor digite um número inteiro");
}
//Função para Verificar se o número escolhido pertence na sequência de Fibonacci
void FibonacciFind(string choose)
{
    int number = int.Parse(choose);
    List<int> fibonacci = new List<int>() { 0, 1 };


    for (int i = 0; i < number; i++)
    {
        // O novo valor a ser adicionado na lista fibonacci, vai ser a soma do anteiror com o atual
        int next = (fibonacci[i]) + (fibonacci[i + 1]);
        fibonacci.Add(next);
    }

    if (fibonacci.Contains(number))
    {
        Console.WriteLine($"O número {number} pertence a sequência.");
    }
    else
    {
        Console.WriteLine($"O número {number} não pertence a sequência.");
    }
}



 (2) Escreva um programa que verifique, em uma string, a existência da letra ‘a’, seja maiúscula ou minúscula, além de
informar a quantidade de vezes em que ela ocorre.

try
{
    Console.Write("\n(2) Digite uma palavra para verificar  a existência da letra ‘a’: ");
    string word = Console.ReadLine()!;
    FindLetterA(word);
}
catch (Exception e) { Console.WriteLine($"Erro: {e.Message}"); }

//Função verifica se para cada letra na palavra desejada é igual a letra 'a', assim ela vai somando ao contador
void FindLetterA(string word)
{
    int count = 0;
    word = word.ToLower(); //aqui garantismos que todas as letras fiquem minúsculas
    
    foreach (char letter in word) 
    {
        if (letter == 'a')
        {
            count++;
        }
    }
    if (count > 0) { Console.WriteLine($"O número de vezes que a letra 'a' aparece na palavra {word.ToUpper()} é {count}. "); }
    else { Console.WriteLine("A letra 'a' não aparece nenhuma vez."); }
    
}
