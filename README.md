using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace WinFormsApp4
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
           
            int kontrolna3 = int.Parse(textBox11.Text);
            int pesel1 = int.Parse(textBox1.Text);
            int pesel2 = int.Parse(textBox2.Text);
            int pesel3 = int.Parse(textBox3.Text);
            int pesel4 = int.Parse(textBox4.Text);
            int pesel5 = int.Parse(textBox5.Text);
            int pesel6 = int.Parse(textBox6.Text);
            int pesel7 = int.Parse(textBox7.Text);
            int pesel8 = int.Parse(textBox8.Text);
            int pesel9 = int.Parse(textBox9.Text);
            int pesel10 = int.Parse(textBox10.Text);
            int kontrolna1 = (pesel1 * 1 + pesel2 * 3 + pesel3 * 7 + pesel4 * 9 + pesel5 * 1 + pesel6 * 3 + pesel7 * 7 + pesel8 * 9 + pesel9 * 1 + pesel10 * 3) % 10;
            int kontrolna2 = 10 - kontrolna1;
            
            int zero = 0;
            
            if(kontrolna2 == 10)
            {
                textBox11.Text = zero.ToString();
            }    
            else if(kontrolna2 != kontrolna3)
            {
                textBox11.Text = kontrolna2.ToString();
            }
            int dataUrodzenia()
            {
                int rok;
                int miesiac;
                rok = 10 * pesel1;
                rok += pesel2;
                miesiac = 10 * pesel3;
                miesiac += pesel4;
                if (miesiac > 80 && miesiac < 93)
                {
                    rok += 1800;
                }
                else if (miesiac > 0 && miesiac < 13)
                {
                    rok += 1900;
                }
                else if (miesiac > 0 && miesiac < 13)
                {
                    rok += 1900;
                }
                else if (miesiac > 20 && miesiac < 33)
                {  
                rok += 2000;
                }
                else if (miesiac > 40 && miesiac < 53)
                {
                rok += 2100;
                }
                else if (miesiac > 60 && miesiac < 73)
                {
                rok += 2200;
                }                
                return rok;
            }
            textBox12.Text = dataUrodzenia().ToString();

            int miesiacUrodzenia()
            {
                int miesiac;
                miesiac = 10 * pesel3;
                miesiac += pesel4;
            if(miesiac > 80 && miesiac <93)
            {
                miesiac -= 80;
            }      
            else if(miesiac >60 && miesiac <70)
                {
                    miesiac -= 60;
                } 
                else if(miesiac >40 && miesiac <53)
                {
                    miesiac -= 40;
                }
            else if(miesiac > 20 && miesiac <33)
                {
                    miesiac -= 20;
                }
                return miesiac;
            }
            textBox13.Text = miesiacUrodzenia().ToString();
            int dzienUrodzenia()
            {
                int dzien;
                dzien = 10 * pesel5;
                dzien += pesel6;
                return dzien;
            }
            textBox14.Text = dzienUrodzenia().ToString();

            char plec()
            {
                if(pesel10 % 2 == 1)
                {
                    return 'M';
                }
                else
                {
                    return 'K';
                }
            }
            textBox15.Text = plec().ToString();

            
        }
    }
}
