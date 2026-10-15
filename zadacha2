import java.io.*;
import java.util.*;

public class Main {

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader("Послпоиск.txt"));

        // Первая строка — служебное число (60000), пропускаем её
        br.readLine();

        List<Long> nums = new ArrayList<>();
        int pairCount = 0;
        final int MAX_PAIRS = 10000;

        String line;
        while ((line = br.readLine()) != null && pairCount < MAX_PAIRS) {
            line = line.trim();
            if (line.isEmpty()) continue;

            String[] parts = line.split("\\s+");
            if (parts.length == 2) {
                long a = Long.parseLong(parts[0]);
                long b = Long.parseLong(parts[1]);
                nums.add(a);
                nums.add(b);
                pairCount++;
            }
        }
        br.close();

        int n = nums.size();
        Long best = null;

        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                long prod = nums.get(i) * nums.get(j);
                if (prod % 21 == 0) {
                    if (best == null || prod < best) {
                        best = prod;
                    }
                }
            }
        }

        if (best == null) {
            System.out.println(-1);
        } else {
            System.out.println(best);
        }
    }
}
