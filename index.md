
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="unicorn/css/bootstrap.min.css">
    <link rel="stylesheet" href="unicorn/css/unicons.css">
    <link rel="stylesheet" href="unicorn/css/owl.carousel.min.css">
    <link rel="stylesheet" href="unicorn/css/owl.theme.default.min.css">
    <link rel="stylesheet" href="unicorn/css/tooplate-style.css">
    <link rel="stylesheet" href="bbc.css">
    <script src="jquery/jquery.min.js" type="text/javascript"></script>
    <script src="jquery/jquery.js" type="text/javascript"></script>
    <script src="jquery/jquery-ui.js" type="text/javascript"></script>
    <title>OguraClutch</title>
</head>
<style>


.thead {
    background-color: #0288df;
    height: 8px !important;
    font-size: 18px !important;
    font-weight: normal !important;
    color: #fff;
    text-align: center !important;
    border-radius: 3px !important;
    border: 1px solid #e6e6e6 !important;
}

.tae {
    

    text-align: center !important;
    border-radius: 3px #cecece !important;


}

.the tr td{
    border: 0px solid #fff !important;
    font-size: 14px;
}
.mr-2{
    font-weight: bold !important;
}

</style>

<?php
$dbquery_position=mssql_query(" SELECT Pos_Name,Pos_Id FROM Position ORDER BY Pos_Name  ASC"); 

$dbquery_department=mssql_query(" SELECT Dep_Name,Dep_Id FROM Department ORDER BY Dep_Name  ASC"); 

$dbquery_nationality=mssql_query(" SELECT DISTINCT Emp_Nationality FROM Employee "); 

$dbquery_group=mssql_query(" SELECT  * FROM Groups "); 

?>
<div class="container-fluid ">

    <div class="row">

        <div class="col-lg-2 col-md-12 col-12 ">
        </div>

        <div class="col-lg-8 col-md-12 col-12 ">

            <table class="table the">
               
                    <tr>

                        <td align="right">

                            <label class="my-1 mr-2  label" for="EmpName">Name :</label>
                        </td>
                        <td>
                            <input type="text" id="EmpName" class="form-control" aria-describedby="passwordHelpInline"
                                name="EmpName" OnKeyPress="ShowEmail();">


                        </td>

                        <td align="right">

                            <label class="my-1 mr-2 label" for="EmpNickName">Nick Name :</label>
                        </td>
                        <td>
                            <input type="text" id="EmpNickName" class="form-control"
                                aria-describedby="passwordHelpInline" name="EmpNickName" OnKeyPress="ShowEmail();">



                        </td>

                    </tr>

                    <tr>

                        <td align="right">

                            <label class="my-1 mr-2 label" for="DepId">Department :</label>
                        </td>
                        <td>
                            <select name="DepId" id="DepId" OnChange="ShowEmail();" class='custom-select'>
                                <option value="">Department All</option>
                                <? while($qry=mssql_fetch_array($dbquery_department))  { ?>
                                <option value="<? echo $qry['Dep_Name'];?>">
                                    <? echo $qry['Dep_Name'];?>

                                </option>

                                <? }?>
                            </select>

                        </td>

                        <td align="right">

                            <label class="my-1 mr-2 label" for="PosId">Position :</label>
                        </td>
                        <td>
                            <select name="PosId" id="PosId" OnChange="ShowEmail();" class='custom-select'>
                                <option value="">Position All</option>
                                <? while($qry=mssql_fetch_array($dbquery_position))  { ?>
                                <option value="<? echo $qry['Pos_Name'];?>">
                                    <? echo $qry['Pos_Name'];?>
                                </option>
                                <? }?>
                            </select>


                        </td>

                    </tr>
                    <tr>
                <td></td>
                <td><a href='EmployeeSave.php?Usr_IdLogin=' class="btn btn-info" role="button" <?
                        echo"$Usr_IdLoginCode"; ?>'>+ AddEmployee</a>
                    <a href='EmployeeAndCom.php?Usr_IdLogin=' class="btn btn-info" role="button" <?
                        echo"$Usr_IdLoginCode"; ?>'>AssetIt</a>
                    
                </td>

            </tr>

                
            </table>


                
                  
      

        </div>
    </div>
    <br>


    <div class="row">

      

        <div class="col-lg-12 col-md-12 col-12 ">




            <div id="ShowEmail"></div>



        </div>
    </div>
</div>
