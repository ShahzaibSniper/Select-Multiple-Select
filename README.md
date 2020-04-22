# Select-Multiple-Select
Select An Item then Auto Select In Multple Select


1:- First Step
    We Need to create an Select Option field
    Here we go...
    ```
    <div class="col-md-3 col-sm-3 ">
        <select id="customerName" onchange="option(this.id, [['companyName', 'data-company-name'],['carName', 'data-car-name'],]);">
            <option value="" selected disabled>Choose..</option>
            <option data-company-name="1" data-car-name="1,2" value="1"> Hassan </option>
            <option data-company-name="2" data-car-name="3" value="2"> Nouman </option>
            <option data-company-name="3" data-car-name="4" value="3"> Khurram </option>
            <option data-company-name="1" data-car-name="1,2" value="4"> Kashif </option>
        </select>
    </div>
    ```
