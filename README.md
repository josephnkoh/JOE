# JOE
ACE MIGRATION
PYSPARK CODE FOR DATA PROCESSING. 

Language - PYTHON.



sc. setLogLevel.("ERROR")

pos = sc.textFile("hdfs:///user/training/CustMkt/staging/pos/pos.dat");
cust = sc.textFile("hdfs:///user/training/CustMkt/staging/customer/*");
salesrep = sc.textFile("hdfs:///user/training/CustMkt/staging/sales_rep/*");
reason_cd = sc.textFile("hdfs:///user/training/CustMkt/staging/return_reason/*");
promolist = sc.textFile("hdfs:///user/training/CustMkt/staging/promotion/*");
storelist = sc.textFile("hdfs:///user/training/CustMkt/staging/store/*");
dept = sc.textFile("hdfs:///user/training/CustMkt/staging/dept/*");
class_data = sc.textFile("hdfs:///user/training/CustMkt/staging/class/*");
vendor = sc.textFile("hdfs:///user/training/CustMkt/staging/vendor/*");
style = sc.textFile("hdfs:///user/training/CustMkt/staging/style/*");

x!=header
header = pos.first()
pos_data = pos.filter(lamba x : x!=header)

header = salesrep.first()
salesrep_data = salesrep.filter(lamba x : x!=header)

$deduplication

unique_salesrep = salesrep_data.distinct();
unique_cust = cust.distinct();
unique_resonCd = reson_cd.distinct();
unique_promolist = promolist.distinct();
$ val unique_pricelist = pricelist.distinct();
unique_depth = dept.distinct();
unique_class = class_data.distinct();
unique_vendor = vendor.distinct(0;
unique_style = style.distinct();
unique_store = storelist.distinct();


unique_salesrep.saveAsTextFile('/user/training/Custmkt/cleanse/unique/salesrep');
unique_cust.saveAsTextFile('/user/training/Custmkt/cleanse/unique/cust');
unique_reasonCd.saveAsTextFile('/user/training/Custmkt/cleanse/unique/reason_cd');
unique_promolist.saveAsTextFile('/user/training/Custmkt/cleanse/unique/promtion');
unique_dept.saveAsTextFile('/user/training/Custmkt/cleanse/unique/dept');
unique_class.saveAsTextFile('/user/training/Custmkt/cleanse/unique/class');
unique_vendor.saveAsTextFile('/user/training/Custmkt/cleanse/unique/vendor');
unique_style.saveAsTextFile('/user/training/Custmkt/cleanse/unique/style');
unique_store.saveAsTextFile('/user/training/Custmkt/cleanse/unique/store');


def main():
         from pyspark import SparkContext
         sc = SparkContext("local", "deduplicate")
         deduplicate(sc)


main()































