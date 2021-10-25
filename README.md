class GFG {
  
// Macros for East, North, South and West
 
// This function returns true if
// the given path is location,
// else false
static boolean isCircular(char path[])
{
  // Initialize starting
  // point for robot as
  // (0, 0) and starting
  // direction as N North
  int x = 0, y = 0;
  int dir = 0;
  
  
  for (int i=0; i < path.length; i++)
  {
      
      char move = path[i];
  
      // If move is left or
      // right, then change direction
      if (move == 'R')
        dir = (dir + 1)%4;
      else if (move == 'L')
        dir = (4 + dir - 1) % 4;
  
      // If move is Go, then
      // change  x or y according to
      // current direction
      else // if (move == 'G')
      {
         if (dir == 0)
            y++;
         else if (dir == 1)
            x++;
         else if (dir == 2)
            y--;
         else // dir == 3
            x--;
      }
  }
  
   
  return (x == 0 && y == 0);
}
  

public static void main(String[] args)
{
    String path_ = "MSMMEMM";
    char path[] = path_.toCharArray();
 
    if (isLocation(path))
      System.out.println("Given sequence" +
      " of moves is Location");
   
}
 
