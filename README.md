 A collection of functions to download, filter and preview the latest ESA Copernicus 5p files produced for a specific location of the world.
 ---
        get5p {get5p}	
        Get a specific S5p product
        Description
        The functions works after get5plist() function, it retrives a specific S5P product and allows to save it
        Usage
        get5p(month, year, number, id, fn)
        Arguments
        month	
        Desired month in mm format (April would be "04", December would be "12")
        year	
        Desired year in yyyy format ("2020" not "20")
        number	
        Desired .csv file index (from 1 to the maximum number of files returned by listlast() function)
        id	
        Desired S5P file index (from 1 to the maximum number of files returned by get5plist() function)
        fn	
        Desired name of the file to be used when saving the product to the local working directory
        Examples
        get5p("04","2020","3","1","lastday.ncf")
        
        ---
        get5plist {get5p}	
        Get a list of 5p products
        Description
        The functions works after listlast(month, year) function. After retrieving the list of available .csv files with listlast(), the get5plist() functions allows to retrieve a list of the available products described inside a specific .csv file.
        Usage
        get5plist(month, year, number)
        Arguments
        month	
        Desired month in mm format (April would be "04", December would be "12")
        year	
        Desired year in yyyy format ("2020" not "20")
        number	
        Desired .csv file index (from 1 to the maximum number of files returned by listlast() function)
        Examples
        get5plist("04","2020","3")
        --
        
        get5p_latlon {get5p}
        Get the latest S5p products (lat long search)
        Description
        The function works by searching the latest 10 products available for a specific location (lat long). It allows to download a specific product after identifying it.
        Usage
        get5p_latlon(lat, lon, id = NULL)
        Arguments
        lat	
        Latitude (degrees) to search at
        lon	
        Longitude (degrees) to search at
        id=NULL	
        If the id parameter is omitted, the function returns a list of up to 10 S5p products available at the given coordinates, if an id is specified the functions downloads the product with the indicated id. If id=-1 then all the found products will be downloaded automatically.
        Examples
        get5p_latlon("44","12")
        get5p_latlon("44","12",1)
        ---
        listlast {get5p}	
        List the latest files available in the Coperniucs 5p catalogue
        Description
        This function search inside the current catalogue of archived products for the Platform Sentinel 5P (https://scihub.copernicus.eu/catalogueview/S5P/) and returns a list of the archived .csv files of a specific month and year.
        Usage
        listlast(month, year)
        Arguments
        month	
        Desired month in mm format (April would be "04", December would be "12")
        year	
        Desired year in yyyy format ("2020" not "20")
        Examples
        listlast("04","2020")
        ---
        plot5p {get5p}	
        Get a S5p product
        Description
        This function allows to inspect a downloaded S5p file or plots it
        Usage
        plot5p(fil, variable = NULL)
        Arguments
        fil	
        Name of the file to inspect/plot
        variable	
        If the field is NULL then the function will return a list containing all the informations of the .nc file. Normally the variables names are included as PRODUCT/variable. If the variable name is given as parameter then the function will plot that variable
        Examples
        plot5p("S5P_OFFL_L2__AER_LH_20200527T115918_20200527T134048_13579_01_010302_20200529T045906.nc")
        plot5p("S5P_OFFL_L2__AER_LH_20200527T115918_20200527T134048_13579_01_010302_20200529T045906.nc","aerosol_index_340_380")
