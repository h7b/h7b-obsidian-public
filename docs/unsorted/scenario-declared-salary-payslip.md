---
createdAt: 2023-06-12T21:23:16+02:00
dg-publish: true
modifiedAt: 2023-06-13T21:08:25+02:00
title: "Difference in benefits when employer declares low gross salary on your payslip"
---
# Difference in benefits when employer declares low gross salary on your payslip

## Overview

Tình huống:
- 1 công ty ở Vietnam lách luật bằng cách khai báo mức lương gộp (gross salary) để đóng báo hiểm thấp hơn so với lương thực trả cho người lao động
- công ty có lợi gì về mặt kinh tế?
- người lao động bị thiệt gì?

Một tình huống khá thú vị mà mình chưa tìm thấy được câu trả lời trên google. Đành tò mò tự ngồi kéo bảng tính để xem người lao động bị thiệt hại nhiều đến mức nào.

Cơ sở để tính dựa trên note về [[hop-dong-lao-dong-va-bao-hiem-xa-hoi-Vietnam|Mức đóng bảo hiểm xã hội bắt buộc, bảo hiểm y tế, bảo hiểm thất nghiệp năm 2023 và Cách tính lương hưu]]

Nhắc lại:

Tổng cộng mức đóng bảo hiểm xã hội, bảo hiểm y tế, bảo hiểm thất nghiệp là 32% trong đó,
- đối với người sử dụng lao động là 21,5% tiền lương theo hợp đồng lao động,
- đối với người lao động là 10,5% tiền lương theo hợp đồng lao động.

Mức lương hưu hàng tháng = Tỷ lệ hưởng lương hưu hàng tháng x Mức bình quân tiền lương tháng đóng BHXH

## Thoughts

Công ty được lợi về việc giảm khoản tiền đóng bảo hiểm bắt buộc khi kê khai lương thấp trên hợp đồng lao động.

Người lao động:
- Được lợi trong hiện tại vì tiết kiệm được khoản tiền đóng bảo hiểm bắt buộc do khai báo lương thấp
- Bị thiệt trong tương lai vì lương hưu bị giảm
- Do "Tỷ lệ hưởng lương hưu hàng tháng" (mức cao nhất 75% nếu người lao động đóng đủ 20 năm) lớn hơn gấp 7 lần so với "Mức đóng bảo hiểm bắt buộc đối với người lao động" (10.5%), nên người lao động sẽ luôn bị thiệt thòi nhiều về mặt kinh tế khi bị buộc phải tham gia 1 hợp đồng lao động như vậy.

Thử minh họa bằng bảng tính:
- Gọi số tiền lương gộp (gross salary) theo hợp đồng lao động là $S_f$
- Tiền lương gộp thực nhận là $S_r$
- Lợi ích về kinh tế của doanh nghiệp: $P_{dn}=0.215*(S_r-S_f)$
- Lợi ích trước mắt trong hiện tại của người lao động: $P_{nld}=0.105*(S_r-S_f)$
- Thiệt hại về kinh tế của người lao động ở 20 năm tới trong tương lai: $L_{nld}=0.75*(S_r-S_f)$
    - Theo khái niệm về [Time Value of Money](https://www.investopedia.com/articles/03/082703.asp), thiệt hại này khi được quy về giá trị hiện tại sẽ là: $PV(L_{nld})=\frac{0.75*(S_r-S_f)}{(1+i)^n}$
- Khoản lỗ ròng trong hiện tại của người lao động khi khai báo lương thấp: $N=P_{nld}-PV(L_{nld})$

## Thiệt hại của người lao động

Lấy ví dụ minh họa qua [bảng tính ggsheet này](https://docs.google.com/spreadsheets/d/1AtmwFi4dduYkv-86zGM1xM5M1vq99eExq4ycAMinEMQ/edit?usp=sharing), tôi thấy rằng với tham số giả định:
- tiền lương gộp (hằng tháng) theo hợp đồng lao động: 5.4trieu VND
- tiền lương gộp (hằng tháng) thực nhận: 15trieu
- tỉ lệ lạm phát ở Vietnam trong 20 năm: 5%/năm

thì mỗi tháng người lao động bị thiệt hại 1.7trieu
- Người lao động hoàn toàn có thể chấp nhận kiểu trả lương kê khai thấp này, nếu cty chịu hoàn trả phần $PV(L_{nld})$ (2trieu654k trong ví dụ này). Chúng ta có thể dùng khoản này đem gửi tiết kiệm hoặc mua các chứng chỉ quỹ thì cũng sẽ tương đương hoặc tốt hơn việc chờ nhận lương hưu ở 20 năm tới trong tương lai
- Nhưng đây là điều hoàn toàn ko khả thi vì cty sẽ phải trả cho người lao động khoản tiền lớn hơn phần $P_{dn}$ (2trieu064k) mà cty được lợi khi lách luật. Nếu vậy thì cty thà làm đúng luật còn hơn!
- Người lao động có thể thử thương lượng để cty chỉ cần bù đắp khoản lỗ ròng $N$ (1trieu700k) thay vì trả đủ phần $PV(L_{nld})$ (2trieu654k). Vì khoản bù đắp $N$ thấp hơn phần $P_{dn}$ mà cty được lợi khi lách luật, nên tôi xem đây là mức hợp lý để có thể đưa lên bàn đàm phán.

Trong kiểu hợp đồng lao đồng khai lương thấp này thì lương thực nhận càng cao, người lao động càng thiệt thòi nhiều. Nếu lương thực nhận là 50trieu, mà chỉ kê khai 5.4trieu thì nghĩa là ở hiện tại, mỗi tháng người lao động bị thiệt 7trieu648k.

Tóm lại, nếu được quyền lựa chọn thì tôi nghĩ chẳng ai lại đi chấp nhận loại hợp đồng kê khai lương thấp hơn thực nhận như vậy.

## Related

- [[hop-dong-lao-dong-va-bao-hiem-xa-hoi-Vietnam|Quy định về Hợp đồng lao động và các chế độ bảo hiểm ở Vietnam]]