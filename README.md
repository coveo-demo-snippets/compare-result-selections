# compare-result-selections

This code works on a Visualforce page. The use case is to compare selections on a hotel, like you would do with Expedia search for example.

1. It uses a TemplateLoader on the result layout for the hotel room to add a inputCheckbox on each result. In the Interface Editor, under CodeView, you can add this code.
```
<div id="search" class="CoveoSearchInterface" data-enable-history="true" data-design="new">


<div class="CoveoFoldingForThread" data-field="@sfcaseid" data-tab="SalesforceCase" data-parent-field="@sfid" data-child-field="@sfcaseid" data-range="0"></div>
<div class="CoveoAnalytics"></div>
<div class="coveo-tab-section"><a class="CoveoTab" data-id="All" data-caption="All Content" data-layout="list"></a>
<div class="CoveoTab" data-id="HotelRooms" data-caption="Hotel Rooms" data-expression="@objecttype=Hotel_Rooms" data-layout="card"></div>

</div>
<div class="coveo-search-section">
    <div class="CoveoSettings"></div>
    <div class="CoveoSearchbox" data-enable-omnibox="true" data-enable-wildcards="true" data-partial-match-keywords="8" data-partial-match-threshold="70%" data-enable-partial-match="true"></div>
    <button id="btnDoSomethingLikeExport" style="display: none" type="button" title="Can create a custom action to do something with all selected items.">Compare</button>
</div>
<div id="coveo-recommendation-main-section" class="coveo-main-section">
    <div id="coveo-recommendation-facet-column" class="coveo-facet-column"><div class="CoveoFacet" data-title="Type" data-field="@objecttype" data-number-of-values="5" data-tab="Salesforce"></div>
<div class="CoveoFacet" data-title="Property" data-field="@property" data-tab="HotelRooms"></div>
<div class="CoveoFacet" data-title="City" data-field="@city" data-tab="HotelRooms"></div>
</div>
    <div id="coveo-recommendation-results-column" class="coveo-results-column">
        <div class="CoveoShareQuery"></div>
        <div class="CoveoPreferencesPanel">
            <div class="CoveoResultsPreferences"></div>
            <div class="CoveoResultsFiltersPreferences"></div>
        </div>
        <div class="CoveoTriggers"></div>
        <div class="CoveoBreadcrumb"></div>
        <div class="CoveoSearchAlerts"></div>
        <div class="coveo-results-header">
            <div class="coveo-summary-section">
                <span class="CoveoQuerySummary"></span>
                <span class="CoveoQueryDuration"></span>
            </div>
            <div class="coveo-result-layout-section">
                <span class="CoveoResultLayout"></span>
            </div>
            <div class="coveo-sort-section">
                <span class="CoveoSort" data-sort-criteria="relevancy" data-caption="Relevance"></span>
<span class="CoveoSort" data-sort-criteria="date descending,date ascending" data-caption="Date"></span>
<span class="CoveoSort" data-sort-criteria="@sfopportunityamountconverted descending,@sfopportunityamountconverted ascending" data-tab="Salesforce" data-caption="Amount"></span>
            </div>
        </div>
        <div class="CoveoHiddenQuery"></div>
        <div class="CoveoDidYouMean"></div>
        <div class="CoveoErrorReport" data-pop-up="false"></div>
        
         <div class="CoveoResultList" data-layout="card" data-wait-animation="fade" data-auto-select-fields-to-include="true" data-fields-to-include="@city, @property, @sfbody, @sfparentname, @coveochatterfeedtopics, @hotelroomqv">

             <script type="text/html" data-field-connectortype="salesforce2" data-field-objecttype="hotel_rooms" data-field-filetype="salesforceitem" class="result-template" id="Hotel Rooms"><div class="coveo-result-frame">  
    <style>
      body, td {
        color: #F8F8F8;
      }
    </style>
    <div class="coveo-result-row" style="margin-bottom: 20px">    
        <div class="coveo-result-cell" style="width:32px; vertical-align:middle; flex-grow:0">          <span class="CoveoIcon" data-small="true"></span>    
        </div>    
        <div class="coveo-result-cell" style="padding-left: 10px"><a class="CoveoSalesforceResultLink" data-always-open-in-new-window="true"></a><br/><span class="CoveoTemplateLoader" data-template-id="inputCheckbox"></span>
</div>  
    </div><div class="coveo-result-row"><div class="coveo-result-cell"><span class="CoveoFieldValue" data-field="@sfsummary" data-html-value="true"></span></div></div>  
    
    <div class="CoveoCardActionBar">    
        <div class="CoveoQuickview"></div>    
        <div class="CoveoCardOverlay" data-title="Details" data-icon="coveo-sprites-main-search-active">      
            <table class="CoveoFieldTable" data-allow-minimization="false">        
                <tbody>    
      
                    <tr data-field="@sfsleepsc" data-caption="Sleep"></tr>           
                    <tr data-field="@sfsquarefeetc" data-caption="Square Feet"></tr>  
                            
                </tbody>      
            </table>
            <div style="padding-left: 10px;" class="CoveoFieldValue" data-field="@sfamenitiesc" data-html-value="true"></div>    
        </div>    
        <div class="CoveoFollowItem"></div>  
    </div>
</div>  
            
            
            </script>
             
         </div>
        <div class="CoveoResultList" data-layout="list" data-wait-animation="fade" data-auto-select-fields-to-include="true" data-fields-to-include="@city, @property, @sfbody, @sfparentname, @coveochatterfeedtopics, @hotelroomqv">



        <script type="text/html" data-field-connectortype="salesforce2" data-field-objecttype="hotel_rooms" data-field-filetype="salesforceitem" class="result-template" id="Hotel Rooms List"><div class="coveo-result-frame">  <div class="coveo-result-row">    <div class="coveo-result-cell" style="width:85px;text-align:center;padding-top:7px;">      <span class="CoveoIcon">      </span>      <div class="CoveoQuickview">      </div>    </div>    <div class="coveo-result-cell" style="padding-left:15px;">      <div class="coveo-result-row">        <div class="coveo-result-cell" style="font-size:18px;"><a class="CoveoResultLink">          </a>
<table class="CoveoFieldTable" data-minimized-by-default="true"><tbody><tr data-caption="Sleep: " data-field="@sfsleepsc"></tr><tr data-caption="Square feet" data-field="@sfsquarefeetc"></tr></tbody></table></div>        <div class="coveo-result-cell" style="width:120px; text-align:right; font-size:12px">          <span class="CoveoFieldValue" data-field="@date" data-helper="date">          </span>        </div>      </div>      <div class="coveo-result-row">              </div>    </div>  </div>  <div class="coveo-result-row">          </div></div>    </script>
          <script id="Default" class="result-template" type="text/html" data-layout="list"><div class="coveo-result-frame">
  <div class="coveo-result-row">
    <div class="coveo-result-cell" style="width:85px;text-align:center;padding-top:7px;"><span class="CoveoIcon">
      </span>
<div class="CoveoQuickview">
      </div>
<span style="font-size:8px;" class="CoveoFieldValue" data-field="@source"></span></div>
    <div class="coveo-result-cell" style="padding-left:15px;">
      <div class="coveo-result-row">
        <div class="coveo-result-cell" style="font-size:18px;">
          <a class="CoveoResultLink">
          </a>
        </div>
        <div class="coveo-result-cell" style="width:120px; text-align:right; font-size:12px">
          <span class="CoveoFieldValue" data-field="@date" data-helper="date">
          </span>
        </div>
      </div>
      <div class="coveo-result-row">
        <div class="coveo-result-cell">
          <span class="CoveoExcerpt">
          </span>
        </div>
      </div>
    </div>
  </div>
  <div class="coveo-result-row">
    <div class="coveo-result-cell" style="width:85px;text-align:center">
    </div>
    <div class="coveo-result-cell" style="font-size:13px;padding-left: 15px;">
      <table class="CoveoFieldTable">
        <tbody>
          <tr data-field="@author" data-caption="Author">
          </tr>
          <tr data-field="@source" data-caption="Source">
          </tr>
          <tr data-field="@language" data-caption="Language">
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>
</script>


        <script type="text/x-underscore-template" id="inputCheckbox">
            <input type="checkbox" id="SelectItem" name="SelectItem" onclick="document.getElementById('btnDoSomethingLikeExport').style.display = 'block';" value="<%-raw.hotelroomqv%>"" />
        </script>


        </div>
        <div class="CoveoPager"></div>
        <div class="CoveoLogo"></div>
        <div class="CoveoResultsPerPage"></div>
</div>
   <div class="coveo-recommendation-column">
      <div id="recommendation" class="CoveoRecommendation" data-design="new" data-results-per-page="5" data-main-search-interface="#search" data-expression="@source==&quot;cust-ceasars-yt&quot;">
        <div class="CoveoAnalytics">
        </div>
        <script class="CoveoRecommendationQuery" type="text/x-query-generic">
        </script>
        <div class="coveo-recommendation-header">
          <div class="CoveoText" data-value="Promotional videos" data-text-align="center" data-weight="bold" data-size="14px">
          </div>
        </div>
        <div class="coveo-recommendation-body">
          <div class="CoveoResultList" data-wait-animation="fade">
            <script id="DefaultRecommendation" class="result-template" type="text/html"><div class="coveo-result-frame">
              <div class="coveo-result-row" style="align-items: center">
                <div class="coveo-result-cell" style="flex-basis:40px; flex-shrink:0; flex-grow:0; text-align:center; width:50px"><span class="CoveoYouTubeThumbnail"></span>
<a class="CoveoResultLink"></a></div>
                
              </div>
              </div>
            </script>
          </div>
        </div>
      </div>
</div>

</div>


<div class="CoveoFieldSuggestions" data-field="@concepts"></div></div>
```


2. On your Visualforce Page, you can include the code in compareResultItems.
