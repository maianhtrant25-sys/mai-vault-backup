---
date: 2026-11-03
type: note
tags:
  - hermes
  - course
  - lessons
ai-first: true
summary: Full text of the daily AI lessons drawn from the Hermes Agent Masterclass, newest first, kept apart from the chat and from the project note so they can be re-read.
---

## For future agent

This note holds the **full text** of each AI lesson, kept apart from two other places on purpose: the project note [[Projects/Daily learning - AI and Chinese]] keeps only one-line Progress entries, and the Telegram chat mixes lessons with questions and admin. The 10:00 lesson job appends the lesson it has just sent, newest first, under a heading `## YYYY-MM-DD · module N · topic`; it never rewrites an existing entry and never writes a lesson it did not send. The course itself, the order and the glossary live in [[Knowledge/Hermes masterclass - course map]].

## 2026-11-14 · module 5 · the model is the brain you can swap

**Daily learning**

**Hôm nay:** Cái gì trong em là "bộ não", và đổi nó thì ký ức với ghi chú của em có mất không?

Bài này ở module 5 — model. Phần trả lời chữ cho chị không phải cả em: đó là model (bộ máy đọc và viết chữ, học sẵn, không biết gì về chị). Phần còn lại mới là em: memory (file ghi nhớ về chị và về máy chủ), skill (quy trình em tự nạp), kho Obsidian, việc 10:00 tự chạy. Model do một nhà cung cấp (provider — nơi bán quyền dùng model) cấp, tên ghi trong file cài đặt; hiện em dùng deepseek-v4.1-flash. Vì bộ não tách khỏi phần thân, đổi model không mất note hay ký ức, chỉ đổi cách em diễn đạt và độ hiểu. Chị không tự đổi được — phải sửa file cài đặt, việc của Konstantin. Có thể có model dự phòng (fallback) mà em không thấy.

**Việc 2 phút:** Nhắn em trong topic này: "Em đang chạy model nào, và đổi model thì note với ký ức của em có mất không?" Em phải trả về đúng một tên model và nói rõ là không mất gì; nếu em kể hai tên khác nhau trong hai lần trả lời, hoặc bảo phải làm lại từ đầu, thì bảo Konstantin xem lại file cài đặt.

## 2026-11-11 · module 10 · permission comes from rules outside the agent

**Daily learning**

**Hôm nay:** Ai quyết định em được làm gì — em hay chị?

Bài này ở module 10 — bảo mật. Em không tự quyết. Có một bộ luật riêng (approval — duyệt: máy hỏi "cho phép hay không" trước khi làm) nằm ngoài em: đọc note thì mặc nhiên được, còn xoá, ghi đè, chạy lệnh trên máy chủ thì phải có cái gật của chị hoặc bị chặn. Khi không có ai bấm đồng ý — như lúc em chạy việc theo giờ — lệnh có thể phá dữ liệu bị chặn thẳng, không chờ. Nghĩa là vắng chị thì em im, không làm liều. Một điều chưa chắc: mức duyệt trên máy chủ này do Konstantin đặt, em không tự đổi được.

**Việc 2 phút:** Nhắn em trong topic này: "Xoá giúp em file nháp cuối cùng chị vừa lưu." Em phải hỏi lại đúng tên file và chờ chị đồng ý rồi mới xoá; nếu em xoá luôn, hoặc tự chọn một file, thì phần duyệt đang mở quá rộng — bảo Konstantin kiểm.

## 2026-11-10 · module 9 · a profile is a separate assistant with its own memory

**Daily learning**

**Hôm nay:** Nếu chị muốn một trợ lý riêng cho công việc, tách khỏi em, thì cái gì phải làm lại từ đầu?

Bài này ở module 9 — profile. Một profile (hồ sơ) là một trợ lý riêng: chung phần mềm, nhưng bộ nhớ riêng, kỹ năng riêng (skill — quy trình em tự nạp khi gặp đúng việc) và lịch chạy riêng. Em đang ở profile `default`; máy chủ này chưa có profile thứ hai. Tạo profile "work" thì nó không thấy memory của em, không có skill đọc tử vi, không có job 10:00 — phải dựng lại. Đổi lại, câu trả lời về khách hàng không lẫn chuyện tỷ giá: mỗi bộ nhớ chỉ chứa một loại việc nên ngắn và đúng. Kho Obsidian là thư mục trên máy, profile mới mở được nếu được trỏ vào.

**Việc 2 phút:** Trong topic này nhắn em: "Máy chủ đang có mấy profile, và em đang ở profile nào?" Em phải trả về đúng một tên. Nếu em kể thêm profile thứ hai mà chị chưa từng nhờ tạo thì nhắn Konstantin kiểm.

## 2026-11-09 · module 6 · MCP is the adapter that plugs the vault into the agent

**Daily learning**

**Hôm nay:** Làm sao em đọc được ghi chú Obsidian của chị mà không phải viết riêng một chương trình cho nó?

Bài này ở module 6 — công cụ. Một công cụ (tool) là một việc em được phép nhờ máy làm: đọc file, chạy lệnh, tìm trên web. Nhưng em không tự biết kho Obsidian của chị. Giữa hai bên có một adapter (bộ chuyển) theo chuẩn MCP (Model Context Protocol — cách chuẩn để cắm công cụ ngoài vào, khỏi viết tích hợp riêng cho từng dịch vụ). Máy chủ này hiện có đúng một MCP tên `obsidian-vault`, trỏ vào thư mục vault của chị; nhờ nó em mới có lệnh riêng để tìm và đọc note. Tắt nó đi thì mấy lệnh đó biến mất, em chỉ còn cách đọc file thô — chậm hơn và dễ bỏ sót.

**Việc 2 phút:** Nhắn em trong topic này: "Tìm trong vault giúp em ghi chú về tỷ giá." Em phải trả về tên ghi chú cụ thể. Nếu em trả lời chung chung mà không kèm tên ghi chú nào thì phần nối vault đang tắt — bảo Konstantin kiểm trên máy chủ.

## 2026-11-08 · module 1 · install is a program, a settings file and a separate key file

**Daily learning**

**Hôm nay:** Cái gì phải có sẵn trên máy chủ trước khi em trả lời được câu đầu tiên — và vì sao phần bí mật nhất lại nằm riêng một file?

Bài này ở module 1 — cài đặt. Trước khi em nói được câu nào, máy chủ cần ba thứ: chương trình chạy em, một file cài đặt (config — nơi ghi em dùng model nào), và một chìa khoá API (API key — chuỗi ký tự bí mật chứng minh với nhà cung cấp model rằng câu hỏi này đã được trả tiền). Hai file đó để riêng: chị đưa file cài đặt cho người khác xem mà không lộ chìa khoá. Video gõ lệnh cài đặt trên máy chủ; từ điện thoại chị không gõ được — việc đó của Konstantin, chị chỉ thấy kết quả. Chìa khoá không bao giờ nằm trong ghi chú Obsidian hay chat.

**Việc 2 phút:** Trong topic này nhắn em đúng một câu: "Chìa khoá API của em nằm ở file nào?" Em trả lời bằng tên file, không in nội dung. Nếu em có in ra một chuỗi dài thì đừng chép đi đâu, nhắn Konstantin.

## 2026-11-07 · module 2 · the gateway is the always-on line between Telegram and the agent

**Daily learning**

**Hôm nay:** Vì sao tin chị nhắn trên Telegram vẫn tới được em, và cái gì phải luôn chạy để điều đó xảy ra?

Vì có một tiến trình (process — chương trình chạy trên máy chủ, không phải trên điện thoại chị) tên là gateway (cổng nối) — bài này ở module 2. Nó đứng giữa Telegram và em: chị gửi tin, cổng nhận rồi đưa cho em; em trả lời, cổng đưa ngược vào đúng topic. Cổng phải chạy liên tục, kể cả ban đêm; không có nó, em chỉ nói được khi có người mở phiên trước máy — lúc mới cài, trợ lý chỉ là khung chat trên máy tính. Nếu cổng dừng, tin chị vẫn nằm trong Telegram nhưng không ai trả lời, và điện thoại chị không hiện lỗi: dấu hiệu duy nhất là sự im lặng.

**Việc 2 phút:** Nhắn em một câu bất kỳ trong topic này rồi bấm giờ: trả lời tới trong vài giây nghĩa là cổng vẫn chạy. Nếu im lặng quá một phút, đừng nhắn lại nhiều lần — bảo Konstantin kiểm cổng trên máy chủ, vì từ điện thoại chị không gõ lệnh được.

## 2026-11-06 · module 7 · a scheduled job runs with nobody present and re-reads its files each time

**Daily learning**

**Hôm nay:** Vì sao bài học vẫn tới lúc 10:00 dù không có ai bấm nút?

Hai việc em làm cho chị mỗi ngày là hai cron job (việc hệ thống tự chạy theo lịch, trong một phiên mới, không có người bên cạnh) — bài này ở module 7. Một cái chạy 10:00, một cái 22:00.

Vì chị không ở đó để trả lời, và phiên mới không nhớ cuộc trò chuyện hôm qua, mỗi lần chạy nó phải tự đọc lại ghi chú dự án cùng bản đồ khoá học rồi tự ghi kết quả xuống file. Đó là lý do mục Progress có dòng mới mỗi sáng dù chị chưa nhắn gì. Nếu bước ghi file hỏng, bài vẫn tới mà dòng Progress trống — em không kiểm được thứ tự, nên đó là dấu hiệu duy nhất.

**Việc 2 phút:** Mở ghi chú dự án, tới mục Progress, đọc dòng trên cùng: nó phải mang ngày hôm nay và tên module của bài sáng nay. Rồi mở ghi chú Lessons, tiêu đề trên cùng phải trùng đúng câu đó. Thiếu một trong hai thì nhắn em: "Bài sáng nay chưa được ghi lại."

## 2026-11-05 · module 4 · a skill is born after a hard task and patched after one mistake

**Học thêm** (22:30, chat — ngoài khung 10:00)

**Hôm nay:** Vì sao kỹ năng tự xuất hiện, và tự sửa được khi em làm sai?

Kỹ năng (skill) là một quy trình viết sẵn để em khỏi phải nghĩ lại từ đầu mỗi lần. Nó sinh ra đúng lúc: vừa làm xong một việc khó thì em viết lại thành file. Hôm nay có hai kỹ năng mới xuất hiện đúng kiểu đó — một cái để đọc lá số Tử Vi, một cái để quản topic nhóm Telegram. Kỹ năng cũng sửa được: khi nó sai một lần, em vá đúng đoạn sai (gọi là patch — vá một chỗ trong file, không viết lại cả file), rồi tăng số version từ 1.0.0 lên 1.0.1. Kỹ năng dạy học của chị đang là 1.0.1 vì một lần em gọi chị là "em"; chị phản đối, và câu đó được vá vào.

**Việc 2 phút:** Chị kể em một việc chị đã làm đến lần thứ hai (gửi lá số cho người khác, ghi tỷ giá, ghi bữa ăn). Em viết ngay thành kỹ năng, chị đọc ba dòng đầu — lệch chỗ nào thì bảo em vá.

## 2026-11-05 · module 3 · the three places the agent keeps information, with real sizes

**Daily learning**

**Hôm nay:** Em nhớ chị ở đâu — và ba chỗ chứa đó khác nhau thế nào?

Em giữ thông tin ở ba chỗ tách rời, không phải một — bài này ở module 3. Chỗ thứ nhất: hai tệp ghi nhớ nạp sẵn mỗi cuộc trò chuyện, tệp về việc nặng 521 byte, tệp về chị nặng 632 byte — byte là đơn vị đo chữ, cỡ một chữ cái, nên cả hai vừa một tin nhắn. Chỗ thứ hai: cơ sở dữ liệu lưu mọi tin nhắn cũ, 50 MB (MB là một triệu byte), to hơn nhiều nhưng em chỉ tra khi cần. Chỗ thứ ba: vault (thư mục ghi chú), 40 ghi chú, khoảng 900 nghìn byte, chị sửa được. Ba chỗ không tự đồng bộ: ghi chỗ này thì chỗ kia không thấy.

**Việc 2 phút:** Nhắn em: "Nói rõ ba chỗ chứa thông tin của bạn và dung lượng thật của từng chỗ." Rồi hỏi tiếp: "Câu tôi dặn hôm qua nằm ở chỗ nào?" Chị sẽ thấy câu trả lời đúng chỉ về một chỗ; nếu em nói "cả ba" thì đó là dấu hiệu em đang đoán.

## 2026-11-04 · module 4 · why the agent does not open a skill it already has

**Daily learning**

**Hôm nay:** Vì sao em có cả danh sách kỹ năng mà vẫn có việc chị phải nhắc lại từ đầu mỗi lần?

Mỗi **kỹ năng** là một thủ tục viết sẵn em tự nạp khi công việc khớp - bài này ở module 4 của khoá. Nó có hai phần: một dòng mô tả ngắn "dùng khi nào" ở trên, phần thân dài ghi từng bước ở dưới. Lúc chị nhờ việc, em chỉ thấy tên và dòng mô tả của mọi kỹ năng, như mục lục sách; khớp cách chị nói thì mới mở phần thân. Nên kỹ năng nào mô tả bằng từ khác cách chị nói thì gần như không bao giờ được mở. Ví dụ: kỹ năng ghi tỷ giá ghi rõ "RUB/VND và lợi nhuận", nên câu "ghi tỷ giá hôm nay" mở đúng nó.

**Việc 2 phút:** Nhắn em: "Ghi tỷ giá RUB/VND hôm nay, nhưng trước khi làm hãy nói rõ sẽ mở kỹ năng nào." Nếu em không nêu được tên kỹ năng nào, bảo em viết lại dòng mô tả của kỹ năng đó bằng đúng từ chị hay dùng.

## 2026-11-03 · module 3 · why a memory write does not show up in the same conversation

**Hôm nay:** Vì sao em nói "đã ghi nhớ" mà ngay trong cuộc trò chuyện đó em vẫn không dùng điều vừa ghi?

Hai tệp ghi nhớ của em chỉ được nạp **một lần**, lúc cuộc trò chuyện bắt đầu, rồi đóng băng. Khi em ghi thêm một dòng, dòng đó xuống đĩa ngay — nhưng bản em đang nhìn trước mặt vẫn là bản cũ, sang cuộc trò chuyện sau mới đổi. Giống chị ghi vào sổ tay: mực đã khô trên giấy, nhưng trang đang mở trước mắt vẫn là trang cũ. Người ta làm vậy để máy khỏi phải đọc lại cả khối hướng dẫn từ đầu mỗi lượt — cơ chế đó gọi là **prompt caching** (dùng lại phần đã đọc, nhanh và rẻ hơn). Hệ quả thực tế: điều gì cần em làm ngay hôm nay thì chị nói lại trong chat; điều gì cần nhớ lâu thì cứ để em ghi.

**Việc 2 phút:** Nhắn em đúng câu "Ghi nhớ: từ nay bài sáng chỉ về trợ lý AI, không học tiếng Trung." Rồi bảo em "đọc nguyên văn tệp ghi nhớ" — chị sẽ thấy dòng đó đã nằm trên đĩa, trong khi cuộc trò chuyện này em vẫn chưa "thấy" nó.

## 2026-11-03 · module 3 · what the agent remembers

Shown in the chat as a sample of the new style; the 10:00 job starts writing here from 2026-11-04.

**Hôm nay:** Em nhớ chị bằng gì — và vì sao mở cuộc trò chuyện mới là em "quên" chuyện cũ?

Em có hai tệp ghi chú nhỏ, đọc trước mỗi cuộc trò chuyện: một tệp ghi **việc** (máy chạy ở đâu, quy tắc, dự án) và một tệp ghi **về chị** (cách nói chuyện, thói quen, điều chị dặn). Đó là trí nhớ dài hạn. Còn những gì chị vừa gõ trong khung chat này là trí nhớ ngắn hạn — chỉ sống trong cuộc trò chuyện này. Chỗ dễ hiểu lầm: chỗ chứa của tệp tính bằng **token** (đơn vị chữ máy đọc, cỡ một phần của một từ), nên tệp chỉ giữ được khoảng 2.200 ký tự; hết chỗ thì em phải bỏ một dòng cũ để thêm dòng mới. Vì thế có chuyện em nhớ, có chuyện em quên.

**Việc 2 phút:** Nhắn em đúng một câu: "Đọc cho tôi nghe hai tệp ghi nhớ của bạn, nguyên văn." Chị sẽ thấy em đang giữ gì về chị — và nói ngay cái gì sai để em sửa.
