//Library for queue in C#



using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Queue1
{
    
    public class Queue<T>
    {
        public class Node
        {
            public T Data { get; set; }
            public Node Next { get; set; }
            public Node (T data)
            {
                this.Data = data;
                Next = null;
            }
            
        }
        private Node Front, Rear= null;
        int count;
        public Queue()
        {
            Front = Rear = null;
             
        }
        //enque an element
        public void Enque(T val)
        {
            Node n = new Node(val);
            if (Rear == null)
            {
                Front = Rear = n;
            }
           
            else
            {
                Rear.Next = n;
              Rear=Rear.Next;
            }
          
        }
        //deque an element
        public T Deque()
        {
            if (Front == null)
            {
                throw new Exception("Queue is Empty");
            }

            T result = Front.Data;
             Node x = Front;
           Front  = Front.Next;
            return result;
        
        }
        //show all current elements of queue
        public void Show()
        {
            if (Front == null)
            {
                Console.WriteLine("Queue is empty");
                return;
            }
          Node y=Front
          while(y!=null)
          {
            T res=y.Data;
            y = y.Next;
            Console.WriteLine(res + " ");
          }

        }

    }
}
 
