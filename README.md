using System;

namespace PhanSo
{
    class PhanSo
    {
        private int TuSo;
        private int MauSo;

        public PhanSo()
        {
            TuSo = 0;
            MauSo = 1;
        }

        public PhanSo(int TuSo, int MauSo)
        {
            this.TuSo = TuSo;
            this.MauSo = MauSo;
        }

        public override string ToString()
        {
            return this.TuSo + "/" + this.MauSo;
        }

        public PhanSo Cong(PhanSo PS2)
        {
            int a = TuSo * PS2.MauSo + MauSo * PS2.TuSo;
            int b = MauSo * PS2.MauSo;
            return new PhanSo(a, b);
        }

        private int UCLN(int a, int b)
        {
            int r = a % b;
            while (r != 0)
            {
                a = b;
                b = r;
                r = a % b;
            }
            return b;
        }
        public PhanSo Tru(PhanSo PS2)
        {
            int a = TuSo * PS2.MauSo - MauSo * PS2.TuSo;
            int b = MauSo * PS2.MauSo;
            return new PhanSo(a, b);
        }

        public PhanSo Nhan(PhanSo PS2)
        {
            int a = TuSo * PS2.TuSo;
            int b = MauSo * PS2.MauSo;
            return new PhanSo(a, b);
        }

        public PhanSo Chia(PhanSo PS2)
        {
            int a = TuSo * PS2.MauSo;
            int b = MauSo * PS2.TuSo;
            return new PhanSo(a, b);
        }


    }




        class Program
    {
        static void Main(string[] args)
        {
            PhanSo PS1 = new PhanSo(2, 5);
            PhanSo PS2 = new PhanSo(3, 7);
            PhanSo Tong = PS1.Cong(PS2);
            PhanSo Hieu = PS1.Tru(PS2);
            PhanSo Tich = PS1.Nhan(PS2);
            PhanSo Thuong = PS1.Chia(PS2);


            Console.WriteLine(Tong);
            Console.WriteLine(Hieu);
            Console.WriteLine(Tich);
            Console.WriteLine(Thuong);

        }
    }
}
