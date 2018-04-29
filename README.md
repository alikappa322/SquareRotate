using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Square
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        int angle=0;
        Timer timer;
        float x,y;
        Graphics g;
        Pen pen;
        private void timer1_Tick(object sender, EventArgs e)
        {
            angle++;
            Invalidate();
        }

        private void pictureBox1_Click(object sender, EventArgs e)
        {
            
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void Form1_Paint(object sender, PaintEventArgs e)
        {
            x = 150;
            y = 100;
            g = this.CreateGraphics();
            pen = new Pen(Color.Black, 2);
            g.TranslateTransform(200, 100);
            g.RotateTransform(angle);
            g.DrawRectangle(pen,0,0, 70, 70);
        }

        private void button1_Click(object sender, EventArgs e)
        {
            timer1.Stop();
            timer2.Start();
        }

        private void timer2_Tick(object sender, EventArgs e)
        {
            angle--;
            Invalidate();
        }

        private void btnFlip_Click(object sender, EventArgs e)
        {
            timer1.Start();
            timer2.Stop();
        }
    }
}
