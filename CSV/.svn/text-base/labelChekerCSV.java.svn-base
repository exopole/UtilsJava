package com.Utils.CSV;

import com.hologramIndustries.labelChekerTest.*;

import java.io.FileWriter;
import java.io.IOException;
import java.util.Vector;

/**
 * Created by admin on 02/05/16.
 */
public class labelChekerCSV {



    /**
     * Method that create a csv file which create 1 file of comparaison between the old and new result.
     *
     * @param path The path where the file is create
     * @param ancientResult The old result
     * @param newresult The new result
     * @param nbrFrame
     */
    static public void createFileCSVComp(String path, LabelChekerAllResult ancientResult, LabelChekerAllResult newresult, Vector<Vector<Integer>> nbrFrame){
        FileWriter fileWriter = null;
        String comma = ";";
        String lineSeparator = "\n";

        try {
            //Initialise the fileWriter
            fileWriter = new FileWriter(path);
            //Add a header
            fileWriter.append("name;Old_Result;New_result;Old_nbrTotalImage;Old_NbrImageLeft;Old_NbrImageRight;New_nbrTotalImage;New_NbrImageLeft;New_NbrImageRight");
            //Add a new line separator after the header
            fileWriter.append(lineSeparator);
            for (int i = 0; i < ancientResult.getSize(); i++) {
                //Add the name of the check
                fileWriter.append(ancientResult.getArrayResult(i).getName());
                fileWriter.append(comma);
                //Add the old result
                fileWriter.append(Integer.toString(ancientResult.getArrayResult(i).getResult()));
                if (newresult.getSize() > i ){ // if the check was reload.
                    fileWriter.append(comma);
                    //Add the new Result
                    fileWriter.append(Integer.toString(newresult.getArrayResult(i).getResult()));
                    fileWriter.append(comma);
                    fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(0).intValue() + nbrFrame.elementAt(i).elementAt(1).intValue()));
                    fileWriter.append(comma);
                    fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(0).intValue()));
                    fileWriter.append(comma);
                    fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(1).intValue()));
                    fileWriter.append(comma);
                    fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(2).intValue() + nbrFrame.elementAt(i).elementAt(3).intValue()));
                    fileWriter.append(comma);
                    fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(2).intValue()));
                    fileWriter.append(comma);
                    fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(3).intValue()));

                }
                fileWriter.append(lineSeparator);

            }

            System.out.println("CSV file was created successfully !!!");
        } catch (Exception e) {
            System.out.println("Error in CsvFileWriter !!!");
            e.printStackTrace();

        } finally {
            try {
                fileWriter.flush();
                fileWriter.close();
            } catch (IOException e) {
                System.out.println("Error while flushing/closing fileWriter !!!");
                e.printStackTrace();
            }

        }


    }
    /**
     * Method that create a csv file which create 1 file of comparaison between the old and new result.
     *
     * @param path path The path where the file is create
     * @param newresult ancientResult The old result
     */
    static public void createFileCSVComp(String path, LabelChekerAllResult newresult, Vector<Vector<Integer>> nbrFrame ){
        FileWriter fileWriter = null;
        String comma = ";";
        String lineSeparator = "\n";

        try {
            //Initialise the fileWriter
            fileWriter = new FileWriter(path);
            //Add a header
            fileWriter.append("CheckName;Comp_Result");
            //Add a new line separator after the header
            fileWriter.append(lineSeparator);
            for (int i = 0; i < newresult.getSize(); i++) {
                //Add the name of the check
                fileWriter.append(newresult.getArrayResult(i).getName());
                fileWriter.append(comma);
                //Add the new Result
                fileWriter.append(Integer.toString(newresult.getArrayResult(i).getResult()));
                fileWriter.append(comma);
                fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(0).intValue() + nbrFrame.elementAt(i).elementAt(1).intValue()));
                fileWriter.append(comma);
                fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(0).intValue()));
                fileWriter.append(comma);
                fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(1).intValue()));
                fileWriter.append(comma);
                fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(2).intValue() + nbrFrame.elementAt(i).elementAt(3).intValue()));
                fileWriter.append(comma);
                fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(2).intValue()));
                fileWriter.append(comma);
                fileWriter.append(Integer.toString(nbrFrame.elementAt(i).elementAt(3).intValue()));

            }
            System.out.println("CSV file was created successfully !!!");
        } catch (Exception e) {
            System.out.println("Error in CsvFileWriter !!!");
            e.printStackTrace();

        } finally {
            try {
                fileWriter.flush();
                fileWriter.close();
            } catch (IOException e) {
                System.out.println("Error while flushing/closing fileWriter !!!");
                e.printStackTrace();
            }

        }


    }


    static public void createFileCSVComp(String path, Vector<LabelCheckerResultatComp> resultatComp ){
        FileWriter fileWriter = null;
        String comma = ";";
        String lineSeparator = "\n";

        try {
            //Initialise the fileWriter
            fileWriter = new FileWriter(path);
            //Add a header
            fileWriter.append("Old_name;New_name;Old_Result;New_result;Old_nbrTotalImage;Old_NbrImageLeft;Old_NbrImageRight;New_nbrTotalImage;New_NbrImageLeft;New_NbrImageRight");
            //Add a new line separator after the header
            fileWriter.append(lineSeparator);
            for (int i = 0; i < resultatComp.size(); i++) {
                //Add the name of the check
                fileWriter.append(resultatComp.elementAt(i).toString());
                fileWriter.append(lineSeparator);
            }
            System.out.println("CSV file was created successfully !!!");
        } catch (Exception e) {
            System.out.println("Error in CsvFileWriter !!!");
            e.printStackTrace();

        } finally {
            try {
                fileWriter.flush();
                fileWriter.close();
            } catch (IOException e) {
                System.out.println("Error while flushing/closing fileWriter !!!");
                e.printStackTrace();
            }

        }

    }



    static public void writeCSVFileOfRegression(Vector<LabelCheckerResultatComp> compList, String path)
    {
        Vector<String> regressionNegative = new Vector<String>();
        Vector<String> regressionPositive = new Vector<String>();
        for (LabelCheckerResultatComp comp :
             compList) {
            if (comp.getRegression() > 0)
                regressionPositive.add(comp.getNameNew());
            else if (comp.getRegression() < 0)
                regressionNegative.add(comp.getNameNew());
        }

        FileWriter fileWriter = null;
        String comma = ";";
        String lineSeparator = "\n";

        try {
            //Initialise the fileWriter
            fileWriter = new FileWriter(path);
            //Add a header
            fileWriter.append("Total_Test;" + compList.size());
            fileWriter.append(lineSeparator);

            fileWriter.append("Total_Difference;" + (regressionNegative.size() + regressionPositive.size()));
            fileWriter.append(lineSeparator);

            fileWriter.append("Amelioration;"+regressionPositive.size());
            for (String name : regressionPositive) {
                fileWriter.append(comma);
                fileWriter.append(name);
            }
            fileWriter.append(lineSeparator);

            fileWriter.append("Regression;" + regressionNegative.size());
            for (String name : regressionNegative) {
                fileWriter.append(comma);
                fileWriter.append(name);
            }
            fileWriter.append(lineSeparator);

            System.out.println("CSV file was created successfully !!!");
        } catch (Exception e) {
            System.out.println("Error in CsvFileWriter !!!");
            e.printStackTrace();

        } finally {
            try {
                fileWriter.flush();
                fileWriter.close();
            } catch (IOException e) {
                System.out.println("Error while flushing/closing fileWriter !!!");
                e.printStackTrace();
            }

        }


    }

}
