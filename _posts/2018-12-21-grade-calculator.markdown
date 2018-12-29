---
title: "GPA Calculator"
layout: post
date: 2018-12-21
tag:
- project
- personal
category: project
author: ayushsm
description: Grade calculator that computes your GPA given your inputted number of units and grades.
---
<html>
    <head>
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css" integrity="sha384-GJzZqFGwb1QTTN6wy59ffF1BuGJpLSa9DkKMp0DgiMDm4iYMj70gZWKYbI706tWS" crossorigin="anonymous">
        <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.6/umd/popper.min.js" integrity="sha384-wHAiFfRlMFy6i5SRaxvfOCifBUQy1xHdJ/yoi7FRNXMRBu5WHdZYu1hA6ZOblgut" crossorigin="anonymous"></script>
        <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/js/bootstrap.min.js" integrity="sha384-B0UglyR+jN6CkvvICOB2joaf5I4l3gm9GU6Hc1og6Ls7i6U/mkkaduKaBhlAXv9k" crossorigin="anonymous"></script>
        <link href='https://fonts.googleapis.com/css?family=Alegreya Sans SC' rel='stylesheet'>
        <style>
            button {
                border-radius: 10px;
                display: block;
                margin: auto;
                padding: 0 2px;
                width: 50%;
            }
            .buttonDiv {
                text-align: center;
            }
            #gpa {
                border-radius: 50%;
                background-color: #87CEFA; 
                height: 300px;
                width: 300px;
                margin: 10px auto;
                line-height: 300px;
                text-align: center;
                font-size: 24pt;
            }
            .header {
                font-weight: bold;
            }
            input {
                width: 100%;
                padding: 12px 20px;
                margin: 0px 0px;
                box-sizing: border-box;
                border-radius: 10px;
                text-align: center;
            }
            input[type=number] {
                width: 50%;
                -moz-appearance: textfield;
            }
            input[type="number"]::-webkit-outer-spin-button,
            input[type="number"]::-webkit-inner-spin-button {
                margin: 0;
                -webkit-appearance: none;
            }
            table {
                font-family: 'Alegreya Sans SC';
                font-size: 22px;
                margin-bottom: 10px;
                text-align: center;
                width: 50%;
            }
            td {
                padding: 10px;
                border: solid 1px;
                text-align: center;
            }
            thead {
                background-color: #87CEFA;
            }
        </style>
    </head>
    <body>
        <form><table id="gradeTable" align="center"> 
            <thead>
                <tr class="header">
                    <td> # </td>
                    <td> Class Name </td>
                    <td> Grade </td>
                    <td> Number of Units </td>
                    <td> Points </td>
                </tr>
            </thead>
            <tbody>
            <tr class="class">
                <td> 1 </td>
                <td><input type="text" id="class"></td>
                <td>
                    <select>
                        <option> A+ </option>
                        <option> A </option>
                        <option> A- </option>
                        <option> B+ </option>
                        <option> B </option>
                        <option> B- </option>
                        <option> C+ </option>
                        <option> C </option>
                        <option> C- </option>
                        <option> D+ </option>
                        <option> D </option>
                        <option> D- </option>
                        <option> F </option>
                    </select>
                </td>
                <td><input type="number"></td>
                <td> 0 </td>
            </tr>
            <tr class="class">
                <td> 2 </td>
                <td><input type="text" id="class"></td>
                <td>
                    <select id="grade">
                        <option> A+ </option>
                        <option> A </option>
                        <option> A- </option>
                        <option> B+ </option>
                        <option> B </option>
                        <option> B- </option>
                        <option> C+ </option>
                        <option> C </option>
                        <option> C- </option>
                        <option> D+ </option>
                        <option> D </option>
                        <option> D- </option>
                        <option> F </option>
                    </select>
                </td>
                <td><input type="number"></td>
                <td> 0 </td>
            </tr>
            </tbody>
        </table></form>
        <div class="buttonDiv">
            <button class="btn btn-primary" onclick="addClass()"> Add Class </button>
        </div>
        <script>
            function addClass() {
                //Variables for rows
                var table = document.getElementById("gradeTable");
                var rowCount = table.rows.length;
                var row = table.insertRow(rowCount);
                //First entry in new row
                var cell0 = row.insertCell(0);
                row.cells.item(0).innerHTML = rowCount;
                //Second entry in new row
                var cell1 = row.insertCell(1);
                var element1 = document.createElement('input');
                element1.type="text";
                cell1.appendChild(element1);
                //Third entry in new row
                var cell2 = row.insertCell(2);
                var element2 = document.createElement('SELECT');
                element2.setAttribute("id", "grade");
                element2.append(new Option("A+"));
                element2.append(new Option("A"));
                element2.append(new Option("A-"));
                element2.append(new Option("B+"));
                element2.append(new Option("B"));
                element2.append(new Option("B-"));
                element2.append(new Option("C+"));
                element2.append(new Option("C"));
                element2.append(new Option("C-"));
                element2.append(new Option("D+"));
                element2.append(new Option("D"));
                element2.append(new Option("D-"));
                element2.append(new Option("F"));
                cell2.appendChild(element2);
                //Fourth entry in new row
                var cell3 = row.insertCell(3);
                var element3 = document.createElement('input');
                element3.type="number";
                cell3.appendChild(element3);
                //Fifth entry in new row
                var cell4 = row.insertCell(4);
                row.cells.item(4).innerHTML = 0;
            }
        </script>
        <div class="buttonDiv">
            <button class="btn btn-danger" onclick="calculate()"> Calculate </button>
        </div>
        <script>
            function calculate() {
                //Dictionary linking letter grade to point value and colors to symbolize grade
                var dict = {};
                dict["A+"] = [4.0, "#008000"];
                dict["A"] = [4.0, "#228B22"];
                dict["A-"] = [3.7, "#9ACD32"];
                dict["B+"] = [3.3, "#F0E68C"];
                dict["B"] = [3.0, "#EEE8AA"];
                dict["B-"] = [2.7, "#FFFF00"];
                dict["C+"] = [2.3, "#FFD700"];
                dict["C"] = [2.0, "#FFA500"];
                dict["C-"] = [1.7, "#FF8C00"];
                dict["D+"] = [1.3, "#FF4500"];
                dict["D"] = [1.0, "#CD5C5C"];
                dict["D-"] = [0.7, "#DC143C"];
                dict["F"] = [0.0, "#FF0000"];
                //Variables for storing key values in calculation of GPA
                var table = document.getElementById("gradeTable");
                var gradePoints = 0;
                var credits = 0;
                var totalPoints = 0;
                //Check if proper credit values
                for (var i = 1; i < table.rows.length; i++) {
                    if ((table.rows[i].cells[3].children[0].value % 1 != 0) || (table.rows[i].cells[3].children[0].value) < 1) {
                        alert("Make sure all your credits are valid whole numbers!");
                        return;
                    }
                }
                //Calcualte points per class
                for (var j = 1; j < table.rows.length; j++) {
                    gradePoints = dict[table.rows[j].cells[2].children[0].value][0];
                    table.rows[j].cells[2].style.backgroundColor = dict[table.rows[j].cells[2].children[0].value][1];
                    credits = table.rows[j].cells[3].children[0].value;
                    table.rows[j].cells.item(4).innerHTML = (credits * gradePoints).toFixed(3);
                    totalPoints = totalPoints + gradePoints;
                }
                var gpa = (totalPoints / (table.rows.length - 1)).toFixed(3);
                //Create new div for GPA if it's not there, but if it is then update it
                var ifgpaDiv = document.getElementById('gpa');
                var roughGrade;
                if (ifgpaDiv) {
                    ifgpaDiv.innerHTML = "Your GPA is:\n" + gpa;
                    if (gpa >= 3.850) {
                        roughGrade = "A+";
                    } else if (gpa >= 3.500) {
                        roughGrade = "A";
                    } else if (gpa >= 3.150) {
                        roughGrade = "A-";
                    } else if (gpa >= 2.850) {
                        roughGrade = "B+";
                    } else if (gpa >= 2.500) {
                        roughGrade = "B";
                    } else if (gpa >= 2.150) {
                        roughGrade = "B-";
                    } else if (gpa >= 1.850) {
                        roughGrade = "C+";
                    } else if (gpa >= 1.500) {
                        roughGrade = "C";
                    } else if (gpa >= 1.150) {
                        roughGrade = "C-";
                    } else if (gpa >= 0.850) {
                        roughGrade = "D+";
                    } else if (gpa >= 0.5) {
                        roughGrade = "D";
                    } else if (gpa >= 0.150) {
                        roughGrade = "D-";
                    } else {
                        roughGrade = "F";
                    }
                    ifgpaDiv.style.backgroundColor = dict[roughGrade][1];
                }
                else {
                    var gpaDiv = document.createElement('div');
                    gpaDiv.id = "gpa";
                    document.body.appendChild(gpaDiv);
                    gpaDiv.innerHTML = "Your GPA is:\n" + gpa;
                    if (gpa >= 3.850) {
                        roughGrade = "A+";
                    } else if (gpa >= 3.500) {
                        roughGrade = "A";
                    } else if (gpa >= 3.150) {
                        roughGrade = "A-";
                    } else if (gpa >= 2.850) {
                        roughGrade = "B+";
                    } else if (gpa >= 2.500) {
                        roughGrade = "B";
                    } else if (gpa >= 2.150) {
                        roughGrade = "B-";
                    } else if (gpa >= 1.850) {
                        roughGrade = "C+";
                    } else if (gpa >= 1.500) {
                        roughGrade = "C";
                    } else if (gpa >= 1.150) {
                        roughGrade = "C-";
                    } else if (gpa >= 0.850) {
                        roughGrade = "D+";
                    } else if (gpa >= 0.5) {
                        roughGrade = "D";
                    } else if (gpa >= 0.150) {
                        roughGrade = "D-";
                    } else {
                        roughGrade = "F";
                    }
                    gpaDiv.style.backgroundColor = dict[roughGrade][1];
                }
            }
        </script>
    </body>
</html>