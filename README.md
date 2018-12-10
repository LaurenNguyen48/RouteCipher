# RouteCipher

import java.util.Arrays;


public class RouteCipher {

    /**
     * A two-dimensional array of single-character strings, instantiated
     * in the constructor.
     */
    private String[][] letterBlock;

    /**
     * The number of rows of letterBlock, set by the constructor
     */
    private int numRows;

    /**
     * Number of columns of letterBlock, set by the constructor
     */
    private int numCols;

    /**
     * You'll need this to test your code. The actual implementation doesn't
     * matter for the test cases though. You just don't want this constructor
     * to cause an error, and you cannot remove it.
     *
     * @param rows
     * @param cols
     */
    public RouteCipher( int rows, int cols ) {
        /* Implement as you see fit */
        numRows = rows;
        numCols = cols;
    
    }

    /**
     * Places a string into letterBlock in row-major order
     *
     * @param str The string to be processed
     *            Postconditions:
     *            if str.length() < numRows * numCols, "A" is placed in each unfilled cell
     *  if str.length() > numRows * numCols, trailing characters are ignored
     */
    private void fillBlock( String str ) {
        /*
         * Implemented in part A
         */
         int cnt = 0;
         
         for(int r = 0; r < numRows; r++){
             for(int c = 0; c < numCols; c++){
                     if(cnt < str.length()){
                         letterBlock[r][c] = str.substring(cnt, cnt + 1);
                     }
                     else{
                         letterBlock[r][c] = "A";
                     }
                     cnt++;
                 }
             }

         
         
        
    }

    /**
     * Extracts encrypted string from letterBlock in column-major order.
     *
     * Precondition: letterBlock has been filled
     *
     * @return The encrypted string from letterBlock
     */
    private String encryptBlock() {
        /* This method is given in the FRQ as "implementation not shown", but
         * is implemented here so that you can use it while writing parts
         * A and B without having to write it yourself. 
         * 
         * It is complete and working. You do not have to do anything to 
         * this method, although since it's here there's a really good
         * chance that you should be calling it. 
         */
        String out = "";
        for ( int c = 0; c < numCols; c++ ) {
            for(int r = 0; r < numRows; r++){
                out = out + letterBlock[r][c];
            }
        }
        return out;
    }


    /**
     * Encrypts a message
     *
     * @param message The string to be encrypted
     * @return The encrypted message. If message is the empty string, returns
     *         an empty string
     */
    public String encryptMessage( String message ) {
        /*
         * Implmented in part B
         */
        String i = "";
        int w = 0;

        while(w < message.length()) {
            fillBlock(message.substring(w);
            i += encryptBlock();
            w += numRows * numCols;
        }

        return i;
         

    }


}
