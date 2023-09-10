# Customer Segmentation & Product Recommendation

### Content Overview 
![Clustering](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/Segmentation-Clustering.png)
#### To help business more understanding about their own customer, segmentation is the good starting point to classify each customer type.
#### When segmentation could be identify, it can help business know their characteristic and initiate action plan more suitable for each customer group.

![Movement](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/Segmentation-Movement.png)

#### Other than segmentation, when time pass by and customer change their behaviour, it can help business make analysis for the rational of change.

# Class activity - HDI Segmentation

### Task 
Understand dataset about membership and transaction of HDI company to analyse customer behaviour by segmentation and perform product recommendation.

## Result of workshop
[Workshop](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/HDI%20-%20Analytics.pdf)

![HDI-Agenda](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/HDI-Agenda.png)

### Project Overview
HDI was started in 1986 as Network Marketing Business in Asia, specifically in Singapore, Malaysia, Indonesia, Hong Kong, and the Philippines. The company offers natural products from bee.

#### Business Objective
From data observation, our team found that the active user was decreased from year to year. So we decided to perform segmentation to identify type of customer to perform the action plan.

#### Dataset
1. data member : master data of downline and his/her sponsor
2. transaction 2021 - 2022 : contains sales by bill from year 2021 to 2022

#### Dataset Limitation
Before perform analytic, our team aware that dataset may incompleted so it may deviate from accurate result.

![Limitation](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/Dataset%20limitation.png)

### Analytic steps
#### 1. Created Dataset for analytic
   - sponsor master : master data of sponsor and no. of downline per sponsor
   - salesbyitem 2021 - 2022 : extract json product file to sales quantiy by item

#### 2. Create single customer view and feature extraction for analytics    

![Feature extraction](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/Feature%20extraction.png)


#### 3. Segmentation

![Segmentation](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/Segmentation%20overview.png)

Our team use colab to perform clustering from Sale transaction 2021 with K-mean model that K = 4.

From the result, we can classified HDI's customer base on information as Grading (Diamond, Gold, Star (Online/Offline))

In addition, we used Sale transaction 2022 to segment customer. We found that some customer had move their segment from PY.

As the result, it can help business to identify the rational of movement to generate action plan to each customer.


#### 4. Product recommendation

![Product recommendation](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/Product%20recommendation%20overview.png)

From list of item, our team use colab to run apriori algorithm that will analyse fequency of item matching and create association rule for further business determination.

Note: Due to limitation of obtain detail of item, we cannot verify the result of algorithm and suggest further action plan for product recommendation.

#### 5. Recal and conclusion

![Recap](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/HDI-Recap.png)

![NextStep](https://github.com/chutima-khun/MADT8101/blob/main/Chapter%2004/HDI-Nextstep.png)



## Lesson Learn & What can improve

### Feedback from AJ. Check
    - เพิ่ม storyline ให้ต่อเนื่องระหว่าง Objective, feature extract, result ทุกอย่าง เพื่อให้สอดคล้องกับ objective ที่เราเปิดมา
    - ตรงรูปเปิด สามารถเพิ่มรายละเอียดให้ชัดเจนขึ้น เช่น acquisition rate / churn rate
    - ตรง teaser สามารถดึงรายละเอียดก่อนบอก limitation เพื่อไม่ให้คนฟังเกิดคำถาม
    - ตรง extraction member ควรมีความละเอียดขึ้น เพื่อให้วิเคราะห์ตรง objective มากกว่านี้ เช่น downline by period/ churn rate/ acquisition rate by period
    - item/transaction สามารถ split ได้ละเอียดกว่านี้
    - Segmentation ยังไม่โชว์ insight สามารถเอา cluster มา run เพิ่มเพื่อหาก๊ปเพิ่มเติม เช่น diamond-frequent, diamond volume จะช่วยในส่วนของการหา action plan ต่อ
    - Feature บางอย่างที่ไม่สอดคล้องหรือทำให้ interupt กับ result ของ model/cluster สามารถดึงออกได้ เช่น CLV 
    - Column ต้อง represent value ให้ชัดกว่านี้ เช่น avg by cluster, avg by person 
    - Movement ถ้าเพิ่มค่าสถิติเพิ่ม เช่นacquisition rate/ churn rate by period จะทำให้ movement ดูมีน้ำหนักมากขึ้น
    - ถ้า split acquisition / churn เข้าไป จะทำให้กราฟชัดขึ้น
    - analysis ยังเป็น assumption ไปหน่อย เช่น gold ที่หายไปมีผลกับ diamond ถ้ามีเวลา น่าจะสามารถ explore ได้มากกว่านี้
    - Product recommend ควรดึงรายการเดี่ยวๆออก และเพิ่ม by basket 
    - min-support จริงๆต่ำไป ถ้าเป็น retail 30-40% ก็ขึ้นมาแล้ว
    - ถ้ามีเวลาน่าจะลองดึง free product ออก
    - Link product recommendation กับ segmentation ให้เห็นภาพมากขึ้น

