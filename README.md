	ĐẠI HỌC QUỐC GIA HÀ NỘI	CỘNG HÒA XÃ HỘI CHỦ NGHĨA VIỆT NAM
	TRƯỜNG ĐẠI HỌC CÔNG NGHỆ	Độc lập - Tự do - Hạnh phúc
		====================
BÁO CÁO BÀI TẬP LỚP MÔN LẬP TRÌNH NÂNG CAO
Sinh viên: Trần Văn Anh 		Sinh ngày: 09/01/2006
Ngành học: Công nghệ thông tin		Lớp: K69-IT3
Tên game: Snake Game (Rắn săn mồi)

Lối chơi, logic của game:
-	Người chơi điều khiển một con rắn di chuyển trên một màn hình lưới.
-	Mục tiêu là ăn các "mồi" xuất hiện ngẫu nhiên trên màn hình.
-	Khi ăn mồi, con rắn sẽ dài ra một ô.
-	Người chơi sử dụng phím Enter để bắt đầu trò chơi, các phím mũi tên (lên, xuống, trái, phải) để điều khiển hướng di chuyển của rắn, khi kết thúc sử dụng phím R nếu muốn chơi lại.
-	Trò chơi kết thúc khi con rắn tự cắn vào thân mình hoặc đâm vào tường.
Đồ họa, âm thanh:
     Đồ họa: 
-	Sử dụng các thư viện đồ họa SDL2, SDL2_image.
-	Rắn được biểu thị bằng các hình ảnh như đầu, thân, đuôi, khúc rẽ gắn lại với nhau (mỗi hình ảnh đề có kích thước 40x40 pixel).
                            
-	Mồi là hình ảnh quả táo (40x40 pixel).
 
-	Background là hình ảnh có kích thước 760x720 pixel (trong đó phần tường bên trái, bên phải và phía dưới có độ rộng là 40 pixel, phần tường phía trên có độ rộng là 80 pixel).
 
•	Khi thua cuộc sẽ có thông báo hiện lên màn hình, điểm số của bạn và hướng dẫn nếu muốn chơi lại.
 
-	Màu sắc tương phản dễ nhìn.
     Âm thanh: 
-	Sử dụng thư viện âm thanh SDL2_mixer.
-	Các hiệu ứng âm thanh được sử dụng (khi ăn mồi, khi thua cuộc).
Ngoài ra còn sử dụng thư viện SDL2_ttf để hiển thị điểm số trên mà hình sau khi ăn mồi (điểm số hiện phía góc trên bên trái màn hình).
Cấu trúc của project game:
- main.cpp:
•	Khởi tạo các biến trò chơi.
•	Khởi tạo rắn, khởi tạo mồi.
•	Xử lí phím bấm trên bàn phím.
•	Vẽ màn hình khi bắt đầu, khi chơi và khi kết thúc.
•	Vẽ rắn khi di chuyển (đi thẳng, rẽ hướng).
- constants.h: file chứa các thông số của chương trình game như màu sắc, kích thước cửa sổ, hướng di chuyển, lưu trữ tọa độ (x, y) của mỗi phân đoạn của rắn trên lưới.
- sdl_utils.h, sdl_utils.cpp:
•	Khởi tạo SDL video (SDL_Init(SDL_INIT_VIDEO)), SDL_mixer (âm thanh, Mix_OpenAudio), SDL_image (hình ảnh, IMG_Init), và SDL_ttf (font chữ, TTF_Init). 
•	Kiểm tra lỗi sau mỗi bước khởi tạo. Nếu có lỗi, in ra thông báo lỗi và trả về false. 
•	Tạo cửa sổ SDL (SDL_CreateWindow). 
•	Tạo renderer SDL (SDL_CreateRenderer). 
•	Load các font chữ bằng TTF_OpenFont. 
•	Trả về true nếu khởi tạo thành công
- game_logic.h, game_logic.cpp: kiểm tra xem rắn có va chạm với tường hay với thân của mình hay không (trả về false nếu có, trả về true nếu không).
- Ngoài ra project còn có các file hình ảnh (đầu, thân, khúc rẽ, đuôi, quả táo, background), file âm thanh (khi ăn mồi, khi thua cuộc), font chữ.
Các chức năng đã cài được cho game:
-	Điều khiển con rắn di chuyển bằng các phím mũi tên. 
-	Tạo mồi ngẫu nhiên trên màn hình không trùng với thân rắn. 
-	Tăng chiều dài con rắn khi ăn mồi. 
-	Kiểm tra va chạm với tường và thân rắn. 
-	Hiển thị điểm số. 
-	Hiển thị thông báo khi thua cuộc. 
-	Âm thanh khi ăn mồi, thua cuộc. 
