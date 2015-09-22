# Windowing-Systems
Assignment 4 Tic Tac Toe Game

package csc4380.TodorGuichin.Assignment4;

//Todor Guichin
//csc4380.001871463.Assignment3
//9/23/2015
//Prof. Frederick


import com.sun.glass.events.KeyEvent;
import java.awt.BorderLayout;
import java.awt.GraphicsDevice;
import java.awt.GraphicsEnvironment;
import java.awt.GridBagConstraints;
import java.awt.GridBagLayout;
import java.awt.GridLayout;
import java.awt.event.MouseEvent;
import java.awt.event.MouseListener;
import javax.swing.BorderFactory;
import javax.swing.Icon;
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JButton;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JOptionPane;




public class TicTacToeTG extends JFrame{
    
    //Jpanels
    JPanel bar = new JPanel();
    JPanel gamePanel = new JPanel(new GridLayout(3,3));    
    
    //JButtons
    JButton topLeft = new JButton();
    JButton topMid = new JButton();
    JButton topRight = new JButton();
    JButton midLeft = new JButton();
    JButton midMid = new JButton();
    JButton midRight = new JButton();
    JButton botLeft = new JButton();
    JButton botMid = new JButton();
    JButton botRight = new JButton();
    
    //player control
    int counter = 0;
    
    //x image and o image
    Icon o = new ImageIcon(getClass().getResource("o.png"));
    Icon x = new ImageIcon(getClass().getResource("x.png"));
    Icon tic = new ImageIcon(getClass().getResource("tic.png"));
    Icon tac = new ImageIcon(getClass().getResource("tac.png"));
    Icon toe = new ImageIcon(getClass().getResource("toe.png"));
    
    //Booleans
    boolean topLeftBool = false;
    boolean topMidBool = false;
    boolean topRightBool = false;
    boolean midLeftBool = false;
    boolean midMidBool = false;
    boolean midRightBool = false;
    boolean botLeftBool = false;
    boolean botMidBool = false;
    boolean botRightBool = false;
    boolean checkForWinner = false;
    boolean playerOne = false;
    
    //JMenuBar
    JMenuBar mnuBar = new JMenuBar();
    
    //JMenu
    JMenu file = new JMenu("File");
    JMenu help = new JMenu("Help");
    
    //JMenuItem
    JMenuItem newGame = new JMenuItem("New Game");
    JMenuItem exit = new JMenuItem("Exit");
    JMenuItem about = new JMenuItem("About");
    
    
    
    
    public static void main(String [] args)
    {
        new TicTacToeTG();
    }
    
    public TicTacToeTG()
    {
        super("csc4380.TodorGuichin.Assignment4");
        
        //super.setJMenuBar(mnuBar);
        setSize(400,400);
        setDefaultCloseOperation(3);
        setResizable(false);
        setVisible(true);
        setFocusTraversalKeysEnabled(false);
        
        GraphicsDevice gd = GraphicsEnvironment.getLocalGraphicsEnvironment().getDefaultScreenDevice();
        
        int width = (gd.getDisplayMode().getWidth() - getWidth()) / 2;
        int height = (gd.getDisplayMode().getHeight() - getHeight()) / 2;
        setLocation(width, height);
        
        //GridBagConstraints
        
        
        
        file.add(newGame);
        mnuBar.add(file);
        super.setJMenuBar(mnuBar);
        
        
        
        
        //set default icons
        topLeft.setIcon(tic);
        topMid.setIcon(tac);
        topRight.setIcon(toe);
        midLeft.setIcon(tac);
        midMid.setIcon(toe);
        midRight.setIcon(tic);
        botLeft.setIcon(tic);
        botMid.setIcon(tac);
        botRight.setIcon(toe);
        
        //gamePanel.setBorder(BorderFactory.createTitledBorder("Tic-Tac-Toe"));
        gamePanel.setSize(400,400);
        
        //add buttons to game panel

        gamePanel.add(topLeft);
        
        gamePanel.add(topMid);
        
        gamePanel.add(topRight);
        
        gamePanel.add(midLeft);
        
        gamePanel.add(midMid);
        
        gamePanel.add(midRight);
        
        gamePanel.add(botLeft);
        
        gamePanel.add(botMid);
        
        gamePanel.add(botRight);
        
        
        
        
        
        
        //add everything to frame
        add(gamePanel);
        
        runGame();
    }
    
    public void runGame()
    {
        
        //topLeftButtonAction
        topLeft.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(topLeftBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        topLeft.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        topLeft.setIcon(x);
                    }
                }
                 topLeftBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //topMidButtonAction
        topMid.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(topMidBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        topMid.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        topMid.setIcon(x);
                    }
                }
                 topMidBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //topRightButtonAction
        topRight.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(topRightBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        topRight.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        topRight.setIcon(x);
                    }
                }
                 topRightBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //midLeftButtonAction
        midLeft.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(midLeftBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        midLeft.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        midLeft.setIcon(x);
                    }
                }
                 midLeftBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //midMidButtonAction
        midMid.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(midMidBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        midMid.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        midMid.setIcon(x);
                    }
                }
                 midMidBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
      
        //midRightButtonAction
        midRight.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(midRightBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        midRight.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        midRight.setIcon(x);
                    }
                }
                 midRightBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //botLeftButtonAction
        botLeft.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(botLeftBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        botLeft.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        botLeft.setIcon(x);
                    }
                }
                 botLeftBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //botMidButtonAction
        botMid.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(botMidBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        botMid.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        botMid.setIcon(x);
                    }
                }
                 botMidBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
        //botRightButtonAction
        botRight.addMouseListener(new MouseListener() {

            @Override
            public void mouseClicked(MouseEvent me) {
                
            }

            @Override
            public void mousePressed(MouseEvent me) {
                
                counter++;
               
                if(botRightBool == true)
                {
                    JOptionPane.showMessageDialog(null,"This space is already used.");
                }
                else
                {
                    if((counter % 2) == 0)
                    {
                        botRight.setIcon(o);
                    }
                    else if((counter % 2 == 1))
                    {
                        botRight.setIcon(x);
                    }
                }
                 botRightBool = true;
                 endGame(checkForWinner);
            }

            @Override
            public void mouseReleased(MouseEvent me) {
                
            }

            @Override
            public void mouseEntered(MouseEvent me) {
                
            }

            @Override
            public void mouseExited(MouseEvent me) {
                
            }
        });
        
    }
    
    private boolean endGame(boolean endGame)
    {
        endGame = false;
        if(counter > 4)
        {
            if((topLeft.getIcon() == topMid.getIcon()) && (topMid.getIcon() == topRight.getIcon()))
            {
                endGame = true;
                if(topLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }

            else if((midLeft.getIcon() == midMid.getIcon()) && (midMid.getIcon() == midRight.getIcon()))
            {
                endGame = true;
                if(midLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }

            else if((botLeft.getIcon() == botMid.getIcon()) && (botMid.getIcon() == botRight.getIcon()))
            {
                endGame = true;
                if(botLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }

            else if((topLeft.getIcon() == midMid.getIcon()) && (midMid.getIcon() == botRight.getIcon()))
            {
                endGame = true;
                if(topLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }

            else if((botLeft.getIcon() == midMid.getIcon()) && (midMid.getIcon() == topRight.getIcon()))
            {
                endGame = true;
                if(botLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }
            
            else if((topLeft.getIcon() == midLeft.getIcon()) && (midLeft.getIcon() == botLeft.getIcon()))
            {
                endGame = true;
                if(botLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }
            
            else if((botRight.getIcon() == midRight.getIcon()) && (midRight.getIcon() == topRight.getIcon()))
            {
                endGame = true;
                if(botLeft.getIcon() == x)
                {
                    playerOne = true;
                    JOptionPane.showMessageDialog(null, "Player One is the Winner");
                }
                else
                {
                    JOptionPane.showMessageDialog(null, "Player Two is the Winner");
                }
            }

        }
        
        return endGame;
        
    }
    
//    public void restartGame()
//    {
//         topLeftBool = false;
//         topMidBool = false;
//         topRightBool = false;
//         midLeftBool = false;
//         midMidBool = false;
//         midRightBool = false;
//         botLeftBool = false;
//         botMidBool = false;
//         botRightBool = false;
//         checkForWinner = false;
//         playerOne = false;
//         counter = 0;
//    }

}

    
