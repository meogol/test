using System;
using System.Collections.Generic;

namespace ConsoleApp3
{
    class Car
    {
        private float vdvig { get; set; }
        /// <summary>
        /// ����� ���������
        /// </summary>
        private int kpos { get; set; }
        /// <summary>
        /// ���-�� ���������� ����
        /// </summary>
        public Car()
        {
            vdvig = 14;
            kpos = 6;
        }

        public Car(float vdvig, int kpos)
        {
            this.vdvig = vdvig;
            this.kpos = kpos;
        }

        public virtual string str()
        {
            string ss= string.Format("����� ��������� {0} ���-�� ���������� ���� {1}", vdvig, kpos); ;           
            return ss;
        }
    }

    class Fcar : Car
    {
        int mas { get; set; }
        /// <summary>
        /// ����� ����
        /// </summary>
        int cc { get; set; }
        /// <summary>
        /// ����������������
        /// </summary>

        public Fcar() :base()
        {
            mas = 2000;
            cc = 800;
        }

        public Fcar(int mas, int cc, float vdvig, int kpos) : base(vdvig, kpos)
        {
            this.mas = mas;
            this.cc = cc;
        }

        public override string str()
        {
            string ss = string.Format("{0} ����� ���� {1} ���������������� {2}", base.str(), mas, cc); ;
            return ss;
        }
    }

    class Tyag : Fcar
    {
        int kPr { get; set; }
        /// <summary>
        /// ���-�� ��������
        /// </summary>
        string typeDv { get; set; }
        /// <summary>
        /// ��� ���������
        /// </summary>

        public Tyag() : base()
        {
            kPr = 1;
            typeDv = "������";
        }
        public Tyag(int kPr,string typeDv, int mas, int cc, float vdvig, int kpo) : base(mas, cc, vdvig, kpo)
        {
            this.kPr = kPr;
            this.typeDv = typeDv;
        }

        public override string str()
        {
            string ss = string.Format("{0} ���-�� �������� {1} ��� ��������� {2}", base.str(), kPr, typeDv); ;
            return ss;
        }
    }

    class Lcar : Car
    {
        float ras { get; set; } 
        /// <summary>
        /// ������
        /// </summary>
        int Mspeed { get; set; }
        /// <summary>
        /// ���� ��������
        /// </summary>

        public Lcar() : base()
        {
            ras = 20;
            Mspeed = 120;
        }
        public Lcar(float ras, int Mspeed, float vdvig, int kpo) : base(vdvig, kpo)
        {
            this.ras = ras;
            this.Mspeed = Mspeed;
        }

        public override string str()
        {
            string ss = string.Format("{0} ������ {1} ���� �������� {2}", base.str(), ras, Mspeed); ;
            return ss;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            var ListCar = new List<Car>() {
                new Car(),
                new Fcar(),
                new Tyag(1,"2",3,4,5,6),
                new Lcar(1,45,12,35)
            };

            foreach (Car n in ListCar)
            {
                string ss=n.str();
                Console.WriteLine(ss);
            }           
            Console.ReadKey();
        }
    }
}
