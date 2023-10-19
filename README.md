import javax.sound.sampled.*;
import java.io.*;

public class TextToSpeech {

    public static void main(String[] args) {
        String textToSpeak = "Hello, this is a Java text-to-speech example.";

        try {
            Synthesizer synthesizer = Central.createSynthesizer(null);
            synthesizer.allocate();

            synthesizer.resume();
            synthesizer.speakPlainText(textToSpeak, null);
            synthesizer.waitEngineState(Synthesizer.QUEUE_EMPTY);

            synthesizer.deallocate();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
} 
