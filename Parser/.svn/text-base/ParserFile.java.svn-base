package com.Utils.Parser;

import android.widget.Toast;

import java.io.File;
import java.io.FileFilter;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.util.Scanner;
import java.util.Vector;

/**
 * Created by admin on 07/03/16.
 */
public class ParserFile {

    static public Vector<String> readFile(String nameFile){
        Vector<String> result = new Vector<String>();
        try {
            Scanner scanner = new Scanner(new FileInputStream(nameFile), "UTF-8");

            while (scanner.hasNextLine()){
                result.addElement(scanner.nextLine());

            }
            scanner.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
        return result;
    }

    static public String[] arrayNameDirectories(String path){
        File myDirectory = new File(path);
        File[] directories = myDirectory.listFiles(new FileFilter() {
            @Override
            public boolean accept(File pathname) {
                return pathname.isDirectory() ;
            }
        });
        String[] nameDirectories = new String[directories.length];
        for (int i=0;i<directories.length; i++) {
            nameDirectories[i] = directories[i].getName();
        }
        return nameDirectories;
    }

    static public File[] arrayDirectories(String path)
    {
        File myDirectory = new File(path);
        File[] directories = myDirectory.listFiles(new FileFilter() {
            @Override
            public boolean accept(File pathname) {
                return pathname.isDirectory() ;
            }
        });

        return directories;
    }

    static public File[] arrayDirectories(String path,  final String strFilter)
    {
        File myDirectory = new File(path);
        File[] directories = myDirectory.listFiles(new FileFilter() {
            @Override
            public boolean accept(File pathname) {
                return pathname.isDirectory() && pathname.getName().contains(strFilter) ;
            }
        });

        return directories;
    }

    static public File fileFromDir(String path,  final String strFilter)
    {
        File myDirectory = new File(path);
        File[] files = myDirectory.listFiles(new FileFilter() {
            @Override
            public boolean accept(File pathname) {
                return pathname.isFile() && pathname.getName().contains(strFilter) ;
            }
        });

        return files[0];
    }



    static public boolean hasDirectories(String path)
    {
        File myDirectory = new File(path);
        File[] directories = myDirectory.listFiles(new FileFilter() {
            @Override
            public boolean accept(File pathname) {
                return pathname.isDirectory() ;
            }
        });

        return directories.length != 0;
    }


    static public String directorieName(String path, String check){
        boolean find = false;
        String[] dirArray = arrayNameDirectories(path);
        String resultDir = "none";
        int i =0;
        while (i<dirArray.length && !find )
            if (dirArray[i].contains(check))
                find=true;
            else
                i++;

        if (i<dirArray.length)
            resultDir = dirArray[i];

        return resultDir;
    }

    static public File lastFileModif(File[] allFile)
    {
        File lastModif = allFile[0];
        for (File f : allFile)
            lastModif = (lastModif.lastModified() < f.lastModified()) ? f : lastModif;
        return lastModif;

    }

}
