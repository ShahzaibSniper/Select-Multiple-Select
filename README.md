# Select-Multiple-Select
Select An Item then Auto Select In Multple Select


1:- First Step
    We Need to create an Select Option field
    Here we go...
    
    <div class="col-md-3 col-sm-3 "> // If you're using Bootstraping
        <select id="customerName" onchange="option(this.id, [['companyName', 'data-company-name'],['carName', 'data-car-name']]);">
            <option value="" selected disabled>Choose..</option>
            <option data-company-name="1" data-car-name="1,2" value="1"> Hassan </option>
            <option data-company-name="2" data-car-name="3" value="2"> Nouman </option>
            <option data-company-name="3" data-car-name="4" value="3"> Khurram </option>
            <option data-company-name="1" data-car-name="1,2" value="4"> Kashif </option>
        </select>
    </div>
    
    Above the code in Select Element we need to do 3(Three) things
    I:- Create Data Attribute in <option> Element
        This Data Attribute have two of types
        =>    This attribute explain/belongs to relevant Select Element
              i:- data-company-name
             ii:- data-car-name
    II:- Create Event Handler in <select> line
        =>    i:- onchange=""
        If onchange(Event Handler) execute (Add Call Function into it), Method will be execute.
        =>    i:- option()
             ii:- Add an Array in this method like
                  =>    [['companyName', 'data-company-name'],['carName', 'data-car-name']]
                  in this array we've id whose belong to data-attribute like
                  if id(id="companyName") is companyName, this relate to data-company-name(attribute) and Select Element
                  so far
                  id(id="carName") is carName, this relate to data-company-name(attribute) and Select Element
        
2:- Second Steop
    Create Mutiple Select Element(Company Name)
    
    <div class="col-md-3 col-sm-3 "> // If you're using Bootstraping
        <select id="companyName" multiple>
            <option value="" selected disabled>Choose..</option>
            <option value="1"> Toyota </option>
            <option value="2"> Honda </option>
            <option value="3"> Suzuki </option>
        </select>
    </div>
    
3:- Third Steop
    Create Mutiple Select Element(Car Name)
    
    <div class="col-md-3 col-sm-3 "> // If you're using Bootstraping
        <select id="carName" multiple>
            <option value="" selected disabled>Choose..</option>
            <option value="1"> Volvo </option>
            <option value="2"> Saab </option>
            <option value="3"> Opel </option>
            <option value="4"> Audi </option>
        </select>
    </div>
    
    
    
4:- Fourth Step
    Create Script to handle all of functionality
    
        var domain_url_str = '',
            domain_url_res = [];

        function option(id, showSlctdOptns) {
            makeAryAny(id, showSlctdOptns);
        }

        function makeAryAny(id, showSlctdOptns) {
            for (var i = 0; i < showSlctdOptns.length; i++) {
                domain_url_str = $("#" + id).find(':selected').attr(showSlctdOptns[i][1]);
                domain_url_res = domain_url_str.split(",");
                rmveSlctdVal(showSlctdOptns[i][0]);
                //$("#" + showSlctdOptns[i][0]).select2("destroy");  // if You're using Select2 Library
                setSelect(showSlctdOptns[i][0]);
                domain_url_res.splice(0, domain_url_res.length);
            }
        }

        function rmveSlctdVal(showSlctdOptns) {
            $("#"+ showSlctdOptns+ " option:selected").prop('selected',false);
        }

        function setSelect(showSlctdOptns) {
            for (var i = 0; i < domain_url_res.length; i++) {
                if (!$('#' + showSlctdOptns + ' option[value="' + domain_url_res[i] + '"]').prop("selected", true).length) {
                    alert('No such option');
                }
                // $("#" + showSlctdOptns).select2(); // if You're using Select2 Library
            }
        }

5:- Fifth Step
    Exit(End)
    if you've to skills to write this code into short to short terms please help us.
    Thanks
    
    
Thanks again to see.
    
