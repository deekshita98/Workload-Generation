# Workload-Generation
Workload generation for Web services with workload characterization and workload modelling

CoreHttpDriver.java (Driver File)

package com.testnscale.sampleweb;
import com.sun.faban.common.NameValuePair;
import com.sun.faban.common.Utilities;
import com.sun.faban.driver.*;
import com.sun.faban.driver.util.ContentSizeStats;
import javax.xml.xpath.XPathExpressionException;
import java.io.IOException;
import java.util.List;
import java.util.concurrent.TimeUnit;
/** * Basic web workload driver drives only one operation via a get request. */
@BenchmarkDefinition (
name = "SampleWeb Workload", version = "0.1", metric = "req/s" )
@BenchmarkDriver (
name = "SampleWeb", threadPerScale = (float)1, opsUnit = "requests", metric
= "req/s", responseTimeUnit = TimeUnit.MILLISECONDS
)
@FixedTime (
cycleType = CycleType.THINKTIME, cycleTime = 0, cycleDeviation = 5
)
@MatrixMix (
operations = {"HomePage", "ProductsPage", "ContactsPage"}, mix = { @Row ({
0, 80, 20 }), @Row ({20, 39, 41 }), @Row ({60, 19, 21 })
})
public class SampleWebDriver {
private DriverContext ctx;
private HttpTransport http;
private String url, homeUrl, productsUrl, contactsUrl;
ContentSizeStats contentStats = null;
/**
