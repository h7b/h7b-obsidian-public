---
createdAt: 2023-06-30T13:02:41+02:00
dg-publish: true
modifiedAt: 2023-07-04T00:38:24+02:00
title: "Coffee market research"
---
# Coffee market research

## Requirements

Báo cáo phân tích thị trường cà phê trinh bày theo biểu đồ về doanh thu và sản luong bao gồm tất cả cafe  gói, lon , chai , dậng bột đóng túi, đóng bao ,...

Nội dung báo cáo gồm :
1. Tổng quan thị trường về XNk cà phê , doanh thu xuất khẩu của Việt nam .
2. Những dạng packaging size phổ biến nhất cho sp cà phê .
3. Sản lượng cà phê nhập khẩu vào 2 thị trường Ấn độ và Trung Quốc. DS Top những nhà nhập khẩu cafe ở 2 Quốc Gia này

## Thoughts

Chủng loại sản phẩm
- cà phê nhân (aka cà phê nhân xanh, nhân xô, nhân thô, green bean)
    - cà phê chè (Arabica)
    - cà phê vối (Robusta)
    - Cà phê chưa rang và khử caffein (HS 090111)
    - Cà phê rang, khử caffein (HS 090112)
    - Cà phê rang chưa khử caffein (HS 090121)
    - Cà phê khử caffein (HS 090122)
    - Vỏ cà phê (HS 090190)
- cà phê chế biến
    - cà phê rang xay
    - cà phê hòa tan
    - cà phê hữu cơ
    - cà phê bột
- Ready-to-drink coffee
    - cà phê đóng lon (keyword: 2101 AND cà phê)
    - nước uống có đường, vị cà phê (keyword: 2202.10 AND cà phê)

possible keywords that I tried in Panjiva

| keywords           | nb shipments | value |
|:------------------ |:------------ |:----- |
| 0901 AND cà phê    | 25k          | 2.4B  |
| cà phê Robusta     | 17k          | 2.2B  |
| cà phê Arabica     | 1.3k         | 148M  |
| cà phê rang        | 1.9k         | 249M  |
| cà phê nhân        | 689          | 83M   |
| cà phê hòa tan     | 1.7k         | 58M   |
| 2101 AND cà phê    | 27k          | 1.1B  |
| coffee drink       | 1.6k         | 13M   |
| cà phê lon         | 85           | 2.7M  |
| 2202.10 AND cà phê | 46           | 11k   |

The shipment values from queries in Panjiva (USD 2.4B max, during the period 2018-2023) are much smaller than the export sales figure (USD 4B for coffee export in 2022 only) published by the General Statistics Office of Vietnam (Tổng cục Thống kê). Hence the limitation in my report is the meaningful of sales value extracted from Panjiva.

## Notes

[Bộ Công thương Vietnam | Thị trường cà phê Anh: Tình hình và triển vọng](https://moit.gov.vn/tin-tuc/thi-truong-nuoc-ngoai/thi-truong-ca-phe-anh-tinh-hinh-va-trien-vong.html)
- Anh đang là thị trường tiêu thụ cà phê lớn thứ 5 châu Âu (sau Đức, Ý, Pháp và Tây Ban Nha)
- Tổng trị giá cà phê tiêu thụ tại Anh hàng năm khoảng 3,9 tỷ Bảng. Trong đó, cà phê hòa tan trị giá 757 triệu Bảng và cà phê rang xay trị giá 446,4 triệu Bảng.
- Top 10 thương hiệu cà phê hòa tan tại Anh năm 2020
- Top 10 thương hiệu cà phê rang xay tại Anh năm 2020
- Hai công ty kinh doanh cà phê hữu cơ hàng đầu gồm Beanberry Coffee Company và Green Bridge Organics.
- Anh quốc là thị trường cà phê thương hiệu lớn nhất châu Âu với 8.222 cửa hàng có thương hiệu, tiếp theo là Đức và Pháp. Năm 2019, thương hiệu cà phê hàng đầu là Costa Coffee với 2.625 cửa hàng, tiếp theo là Greggs với 1.048 cửa hàng và Starbucks với 995 cửa hàng.
- xuất khẩu cà phê của Việt Nam sang Anh năm 2020 đạt 27.915 tấn, trị giá hơn 48 triệu USD
- Về khẩu vị, người Anh không uống cà phê đậm đặc như cà phê đen của Việt Nam. Cà phê thành phẩm có mùi và vị mạnh quá sẽ khó bán ở thị trường Anh.
- Các doanh nghiệp cà phê Việt Nam nên chào bán các lô hàng nhỏ hơn nhưng có chất lượng đồng đều hơn
- áp dụng công nghệ chế biến hiện đại hơn (ví dụ như cách thức ủ men, tẩm mật ong, yếm khí) để gia tăng chất lượng sản phẩm
- cải thiện mẫu mã bao đựng cà phê (ví dụ in những câu chuyện ngắn lên bao cà phê như Mexico đã làm). Bao cà phê bằng vải đay có khối lượng 30 kgs sẽ bắt mắt hơn và được các nhà rang xay chào đón hơn bao cà phê bằng nilon trắng

[Lan tỏa thương hiệu cà phê Việt](https://baotintuc.vn/long-form/emagazine/lan-toa-thuong-hieu-ca-phe-viet-20230311111235340.htm)
- Việt Nam hiện là quốc gia đứng thứ hai thế giới sau Brazil về thị phần xuất khẩu cà phê
- Các loại cà phê trồng phổ biến ở Vietnam: cà phê vối (Robusta), cà phê chè (Arabica), cà phê mít (Liberia), Culi, Cherry, Moka. Trong đó, 90% diện tích cà phê là cà phê vối, kế đến là cà phê chè với khoảng 10% và cuối cùng là cà phê mít với một tỷ lệ rất nhỏ

[Trung tâm thông tin phát triển nông nghiệp nông thôn | Báo cáo thường niên cà phê năm 2022](http://agro.gov.vn/images/files/Báo%20cáo%20Thường%20niên%20cà%20phê%20năm%202022.pdf)
- Năm 2022, xuất khẩu cà phê của Việt Nam đạt 1,7 triệu tấn, trị giá xấp xỉ 3,9 tỷ USD
- Năm 2022, Việt Nam vẫn chủ yếu xuất khẩu các loại cà phê thô với hàm lượng giá trị gia tăng thấp như cà phê chưa rang chưa khử cafein với 3,1 tỷ USD, chiếm 81,5% tổng kim ngạch xuất khẩu. Cà phê hoà tan xuất khẩu đứng thứ hai với 434,9 triệu USD, chiếm 11,3% tổng kim ngạch xuất khẩu
- Hình 13: Thị trường xuất khẩu cà phê Việt Nam, 2021 - 2022 (p.16). Năm 2022, Đức vẫn tiếp tục là quốc gia nhập khẩu cà phê nhiều nhất của Việt Nam, tiếp theo là Hoa Kỳ, thứ ba là Nhật Bản
- Bảng 2: Sản lượng, xuất khẩu và tiêu thụ cà phê của Việt Nam 2020-2023 (p.20)

[ritachi | Tiêu chuẩn cà phê xuất khẩu](https://ritachi.com/tieu-chuan-ca-phe-xuat-khau/)
- Hiện nay thị trường cà phê xuất khẩu được chia làm 3 phân khúc liên quan và hình thành nên những tiêu chuẩn tương đối rõ rệt
    - Thị trường cà phê đặc sản (Specialty Coffee)
        - là một thị trường ngách, mới nổi trong thời gian gần đây và đang có xu hướng tăng trưởng mạnh mẽ
        - cà phê được công nhận là đặc sản khi có điểm thử nếm từ 80 điểm trở lên (trên thang điểm cao nhất là 100 điểm) bởi các chuyên gia có chứng chỉ hành nghề thử nếm chất lượng. Hệ thống tiêu chuẩn này được vận hành và chi phối bởi Hiệp hội cà phê đặc sản thế giới [Specialty Coffee Association (SCA)](https://sca.coffee/), Viện quản ly chất lượng cà phê – [Coffee Quality Institute (CQI)](https://www.coffeeinstitute.org/) hoặc các thành viên thuộc ủy quyền từ 2 tổ chức này
    - Thị trường cà phê chất lượng cao (Premium Coffee)
        - Là thị trường cà phê có chọn lọc, bước đầu chất lượng cà phê được chú trọng trong sản xuất, thu hái và chế biến tuy nhiên chưa đạt được ngưỡng chất lượng cà phê đặc sản, có điểm chất lượng thử nếm dao động trong khoảng 70 – 79 điểm
        - một số tên gọi, phân loại khác về thị trường cà phê trong phân khúc này như cà phê có chứng nhận bền vững (Fairtrade, Rainforest, 4C, UTZ, Bird Friendly, Shade-grown …), Cà phê hữu cơ Organic, Cà phê dành cho người sành ăn Gourmet
    - Thị trường cà phê thương mại (Commodity Coffee)
        - Là thị trường cà phê lớn nhất hiện tại, đa phần các khách hàng nhập khẩu, nhà rang xay sẽ tìm đến Việt Nam để thu mua dòng sản phẩm này
        - Nhược điểm lớn nhất của thị trường này đó chính là do cơ sở đánh giá chất lượng dựa trên cảm quan màu sắc và tỷ lệ hạt lỗi, chưa chú trọng đến chất lượng hương vị thử nếm nên dẫn đến tình trạng chất lượng có thể không đồng nhất giữa các lô hàng
- Tiêu chuẩn cà phê xuất khẩu nhân xanh (Green Coffee) Việt Nam
    - Tiêu chuẩn này áp dụng cho 2 loại cà phê chính của Việt nam bao gồm cà phê chè (Arabica) và cà phê vối (Robusta)
    - Văn bản [Tiêu chuẩn cà phê xuất khẩu TCVN 4193:2014](https://tieuchuan.vsqi.gov.vn/tieuchuan/view?sohieu=TCVN+4193%3A2014)
    - Tiêu chuẩn phân hạng chất lượng cà phê nhân sẽ dựa trên việc xác định tỷ lệ các hạt lỗi, khuyết tật
    - Tiêu chuẩn cà phê Arabica xuất khẩu. Thêm 2 phương pháp chế biến phổ biến mà khách hàng thường hỏi là arabica Wash/Fully wash (chế biến ướt) và unWash
    - Tiêu chuẩn cà phê Robusta xuất khẩu. Thêm các phương pháp chế biến phổ biến mà khách hàng thường hỏi là: Wet polish, Clean, Standard (G1, G2, G3)
    - 5 tiêu chuẩn phổ biến trong các hợp đồng xuất khẩu cà phê bao gồm
        - Độ ẩm (M – Moisture): nhỏ hơn hoặc bằng 12,5%
        - Tỷ lệ nhân lỗi hạt đen, vỡ (BB – Black& Broken beans): 2% max
        - Tỷ lệ tạp chất (FM – Foreign Matter): 0.5 % max
        - Quy cách đóng gói, bảo quản (Packaging): bao PP hoặc Jute bag – 60kg
        - Khối lượng: 1 container 20ft (19,2 tấn)
    - `Tiêu chuẩn cà phê xuất khẩu loại 1` chính là tiêu chuẩn cao nhất đối với phân khúc cà phê thương mại. Những tiêu chuẩn này áp dụng cho cà phê nhân xuất khẩu cũng chính là tiêu chuẩn nguyên liệu đầu vào tương ứng cho các nhà rang xay xuất khẩu
- Tiêu chuẩn cà phê xuất khẩu sang Mỹ
- Tiêu chuẩn xuất khẩu cà phê sang Châu Âu
- Tiêu chuẩn xuất khẩu cà phê sang Nhật Bản
- Tiêu chuẩn xuất khẩu cà phê sang Trung Quốc
- phân định rõ 2 hệ thống yêu cầu là theo xếp hạng thang điểm chất lượng (đối với cà phê chất lượng cao, đặc sản) và theo giấy phép xuất khẩu (đối với cà phê thương mại)

[Asia target | Cà phê Việt Nam tại thị trường châu Âu sau EVFTA: Cơ hội, thách thức và giải pháp](https://www.asiatarget.vn/blogs/global-sourcing/san-xuat-va-xuat-khau-ca-phe)
- Với sản lượng lớn nhưng các doanh nghiệp cà phê của Việt Nam hiện chủ yếu vẫn xuất khẩu thô (cà phê nhân) mà chưa tham gia được vào chế biến sâu và rang xay xuất khẩu. Hầu hết cà phê trong nước được thu gom thông qua các đại lý, doanh nghiệp nhỏ rồi bán lại cho các công ty, doanh nghiệp lớn trong nước và FDI sơ chế (cà phê nhân) rồi xuất khẩu.
- cơ hội đến từ cắt giảm thuế quan của EU đối với cà phê nhập khẩu từ Việt Nam. Với cam kết xóa bỏ thuế quan theo EVFTA, cà phê của Việt Nam xuất khẩu sang EU sẽ có 93% dòng thuế về 0% ngay khi Hiệp định có hiệu lực. Theo đó, EU sẽ xóa bỏ ngay mức thuế 7,5% - 9,0% đối với cà phê nhân (rang, rang xay). Đối với một số chế phẩm từ hạt cà phê bao gồm cà phê hòa tan, tinh chất chứa cà phê mức thuế 9,0% - 11,5% sẽ được xóa bỏ trong vòng 3 năm.
- cơ hội đến từ việc EU cam kết bảo hộ 39 chỉ dẫn địa lý của Việt Nam liên quan tới nông sản nổi tiếng có tiềm năng xuất khẩu cao, trong đó có sản phẩm cà phê Buôn Ma Thuột
- cà phê nhân xanh xuất khẩu sang EU theo nguyên tắc của EVFTA cần đáp ứng quy tắc xuất xứ thuần túy, tức là 100% phát triển từ vùng nguyên liệu tại Việt Nam.
- Đối với các chế phẩm từ cà phê: không tái sản xuất lại từ các sản phẩm không xuất xứ trong cùng nhóm với sản phẩm đầu ra.
- Trọng lượng đường sử dụng trong sản phẩm không được vượt quá 40% trọng lượng sản phẩm.
- chỉ có nhóm cà phê chế biến mới được hưởng lợi từ cắt giảm thuế quan vì các nhóm cà phê thô đã có mức thuế suất nhập khẩu bằng 0 trước khi có EVFTA. Trong khi đó tỷ lệ cà phê rang xay hiện nay chỉ chiếm chưa đến 10% tổng lượng cà phê xuất khẩu của Việt Nam. Thực tế này đòi hỏi các doanh nghiệp sản xuất và chế biến cà phê cần đầu tư vào chế biến sâu, tăng tỷ trọng xuất khẩu cà phê chế biến để có thể được hưởng lợi từ việc cắt giảm thuế quan theo EVFTA
- Hiện nhu cầu của thị trường EU đối với các loại cà phê chế biến và cà phê chất lượng cao đang trong xu hướng tăng lên
- Hiện tại dù chất lượng và sản lượng cà phê nổi tiếng thế giới, song các thương hiệu cà phê Việt Nam vẫn còn lưa thưa và mờ nhạt. Do các nhà sản xuất không tự tay chế biến sâu và xuất khẩu trực tiếp, cà phê chế biến chủ yếu xuất hiện dưới tên của những thương hiệu nước ngoài, các đại lý thu mua chính hạt cà phê Việt Nam và sau đó đổi tên để tiến hành xuất khẩu
- Nhu cầu tìm kiếm cà phê ngon và chất lượng cao là chung ở khắp EU. Như tại Hà Lan, 80% người tiêu dùng chọn Arabica, còn lại 20% là Robusta. Dòng cà phê hạt Colombia; hương vị việt quất, socola, hạt phỉ và mận là loại và hương vị cà phê được ưa chuộng nhất tại Hà Lan với doanh thu cao nhất trong dòng cà phê nguyên hạt, đóng trong túi 500g giá khoảng 11 - 15 EUR
- Pháp được coi là thị trường tiềm năng đối với các nhà xuất khẩu cà phê, đặc biệt là phân khúc cà phê cao cấp. Dự tính, thị trường cà phê cao cấp có thể tăng từ 2% trong số 300.000 tấn bán ở Pháp mỗi năm lên 10% thị phần vào năm 2025
- Trong khi người Việt Nam ưa chuộng cà phê đậm, đắng của Robusta khi pha bằng phin và thêm sữa đặc thì người EU lại thích cà phê Arabica với vị nhạt hơn và chua.

[Bộ Công thương | Thông tin xuất khẩu vào thị trường EU ngành hàng cà phê](https://wtocenter.vn/file/18163/cafe_0846.pdf)
- Cà phê Arabica - dòng cà phê được ưa chuộng ở châu Âu
- Những năm gần đây, Việt Nam đã chuyển hướng mạnh sang sản xuất cà phê có chứng nhận bền vững. Việt Nam đứng thứ 3 về diện tích cà phê được chứng nhận bền vững chỉ sau Brazil và Colombia
- Trong số các thị trường thành viên EU, cà phê Việt Nam được xuất chủ yếu sang các nước: Đức, Italia, Tây Ban Nha, Bỉ và Pháp. Số liệu 2019 (p.4)
- Chủng loại cà phê eu nhập khẩu từ việt nam năm 2019 và thị phần (p.5). Mã HS. 090111 (Cà phê chưa rang và khử caffein) là chủng loại được xuất khẩu nhiều nhất sang EU
- Nắm giữ vai trò chính trong các kênh phân phối trên thị trường cà phê EU là những công ty có thị phần và thương hiệu lớn như Caffe Nero, Coffee Beanery, Coffee Republic, Costa Coffee, Dunkin 'Donuts, Keurig Green Mountain, Kraft Heinz, Mauro Demetrio, McCafe, Nestle, Segafredo, Starbucks, Strauss Group và Tim Hortons.
- cam kết xóa bỏ thuế quan theo EVFTA
- Quy tắc xuất xứ đối với cà phê theo EVFTA: Để được hưởng các ưu đãi thuế quan theo EVFTA, cà phê phải có xuất xứ thuần túy, tức là được trồng tại Việt Nam. Đối với các chế phẩm từ cà phê: không tái sản xuất lại từ các sản phẩm không xuất xứ trong cùng nhóm với sản phẩm đầu ra; và trọng lượng đường sử dụng trong sản phẩm không được vượt quá 40% trọng lượng sản phẩm.
- Quy định, tiêu chuẩn kỹ thuật để xuất khẩu vào EU

## Related

- [[netherlands-market-research-soft-drinks|Market research of soft drinks and juice for Nawon]]
- [Bộ Công thương Vietnam | Thị trường cà phê Anh: Tình hình và triển vọng](https://moit.gov.vn/tin-tuc/thi-truong-nuoc-ngoai/thi-truong-ca-phe-anh-tinh-hinh-va-trien-vong.html)
- [Lan tỏa thương hiệu cà phê Việt](https://baotintuc.vn/long-form/emagazine/lan-toa-thuong-hieu-ca-phe-viet-20230311111235340.htm)
- [Trung tâm thông tin phát triển nông nghiệp nông thôn | Báo cáo thường niên cà phê năm 2022](http://agro.gov.vn/images/files/Báo%20cáo%20Thường%20niên%20cà%20phê%20năm%202022.pdf)
- [wtocenter | Xuất khẩu cà phê - nhiều về lượng, yếu về thương hiệu](https://trungtamwto.vn/chuyen-de/22854-xuat-khau-ca-phe--nhieu-ve-luong-yeu-ve-thuong-hieu)
- [ritachi | Tiêu chuẩn cà phê xuất khẩu](https://ritachi.com/tieu-chuan-ca-phe-xuat-khau/)
- [Asia target | Cà phê Việt Nam tại thị trường châu Âu sau EVFTA: Cơ hội, thách thức và giải pháp](https://www.asiatarget.vn/blogs/global-sourcing/san-xuat-va-xuat-khau-ca-phe)
- [Bộ Công thương | Thông tin xuất khẩu vào thị trường EU ngành hàng cà phê](https://wtocenter.vn/file/18163/cafe_0846.pdf)
- [The International Coffee Organization (ICO)](https://icocoffee.org/)